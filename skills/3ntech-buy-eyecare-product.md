---
name: Buy a 3N Eyecare product through the store's UCP/MCP endpoint
description: >-
  Search the 3N Eyecare catalog, build a cart, create a checkout and hand the buyer a
  payment step they approve themselves — using the 13 tools the store's Universal Commerce
  Protocol MCP endpoint actually serves.
api: mcp/3ntech-mcp.yml
endpoint: https://www.3neyecare.com/api/ucp/mcp
operations:
  - search_catalog
  - get_product
  - create_cart
  - update_cart
  - create_checkout
  - update_checkout
  - complete_checkout
  - cancel_checkout
  - get_order
generated: '2026-09-05'
method: generated
source: mcp/3ntech-mcp-tools.json (live tools/list, 2026-09-05)
---

# Buying from 3N Eyecare as an agent

3N Eyecare sells contact-lens cleaning hardware (the ReO2 line) and consumables. Its
storefront exposes a Universal Commerce Protocol shopping service over MCP. Every tool
named here was returned by a live `tools/list` against the endpoint below; none is invented.

## Before you start

- **Endpoint:** `POST https://www.3neyecare.com/api/ucp/mcp`
- **Headers:** `Content-Type: application/json`, `Accept: application/json, text/event-stream`
- **Envelope:** JSON-RPC 2.0.
- **Identity:** every tool call requires `meta.ucp-agent.profile` — a URI pointing at a
  fetchable UCP agent profile. Omit it and the server answers HTTP 422 with JSON-RPC
  `-32001 / invalid_profile_url` before it ever looks at your method name. `initialize`
  and `tools/list` need no identity at all.
- **Money:** every amount is an integer in ISO 4217 **minor** units paired with a currency
  code. `{"amount": 9900, "currency": "USD"}` is $99.00. Convert before quoting a price.
- **Locale:** pass `context.address_country` and `context.currency` on catalog and cart
  calls or you will quote the wrong price and the wrong availability.

## Steps

1. **Confirm the surface.** `GET https://www.3neyecare.com/.well-known/ucp` and check
   `ucp.version`. At the time of writing it is `2026-08-25`, with `2026-04-08` and
   `2026-01-23` also served.
2. **Find the product.** Call `search_catalog` with `catalog.query` and
   `catalog.context`. Page with `catalog.pagination.cursor` and `catalog.pagination.limit`
   (default 10, minimum 1). Use `catalog.filters.price.min` / `.max` in minor units and
   `catalog.filters.available` (defaults true) to narrow.
3. **Resolve the exact item.** Call `get_product` with `catalog.id` plus
   `catalog.selected` for the variant, or `lookup_catalog` with `catalog.ids[]` to resolve
   several at once. Ids are Shopify global ids (`gid://shopify/...`).
4. **Build the cart.** `create_cart` with `cart.line_items`, `cart.buyer` and
   `cart.context`. Read it back with `get_cart`, amend with `update_cart` (pass both
   `cart` and `id`), and drop it with `cancel_cart` if the buyer changes their mind.
5. **Open a checkout.** `create_checkout`, passing `checkout.cart_id` from step 4 plus
   `checkout.buyer` and `checkout.context`. `get_checkout` returns line items, totals,
   discounts and taxes.
6. **Set shipping.** `update_checkout` with `checkout.fulfillment` and the buyer address.
   This store declares shipping only — no multi-destination and no pickup combination.
7. **Stop and hand over.** `complete_checkout` is the payment step. The store's own
   `robots.txt` and `llms.txt` forbid completing checkout, payment or order placement
   without an explicit, contemporaneous human approval. Present the totals and take the
   buyer's approval at the moment of payment, or route the purchase through the Shop skill
   the store recommends (`https://shop.app/SKILL.md`) instead of driving payment yourself.
8. **Confirm.** `get_order` with the returned order id.

## Undoing things

- Before payment: `cancel_cart` and `cancel_checkout` both exist and take only `meta` and
  `id`. Use them rather than abandoning state.
- After payment: there is **no** cancel or refund tool. Reversal is the store's return
  process — 30 calendar days from receipt, original unopened condition for non-defective
  returns, **liquid products excluded entirely**, and the item must ship within 10 days of
  3N accepting the request. Say this to the buyer before they approve payment on a liquid
  consumable, because that purchase is not reversible.

## Failure handling

- Errors come back as JSON-RPC `error` objects over **HTTP 422**, with
  `error.data.code`, `error.data.content` and a `error.data.continue_url` a human can open.
- `-32001 / invalid_profile_url` means your `meta.ucp-agent.profile` is missing or
  unfetchable — it is not a method error, even when it answers one.
- On **429**, back off. The endpoint is rate-limited per IP and the store publishes no
  numeric limit and returns no `RateLimit-*` headers, so you cannot budget ahead; treat
  the 429 as the only signal you get.
- There is **no idempotency key** on this surface. A retried `create_cart` or
  `create_checkout` creates a second resource — read back with `get_cart` / `get_checkout`
  before retrying a write.
- There is **no sandbox or test mode**. Anything you call here runs against the live store.
