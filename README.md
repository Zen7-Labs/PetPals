# PetPals · Conversational Commerce on ChatGPT

> **PetPals** is a pet-supply shopping app that lives **inside ChatGPT** — and on the web — so shoppers can discover products, build a cart, and check out without ever leaving the conversation. One account, one cart, one order history, across both surfaces.
>
> **Try it on ChatGPT:** https://chatgpt.com/apps/petpals/asdk_app_697047972e8c8191a13a465c9480d508
> **Website:** https://platform.zen7.com

---

## The pitch

Most e-commerce experiences today force the shopper to leave the conversation: they ask a friend (or an AI) what to buy, then jump to a website, search again, sift through listings, manage a cart, log in, type an address, pay. Every step bleeds intent.

PetPals collapses that funnel. A shopper who asks ChatGPT "*what's a good kitten food for a picky 3-month-old?*" gets:

1. **Real products** rendered as a rich card right in the chat — not a link, not a description.
2. A **cart** they can grow over the course of the conversation.
3. **Checkout** without leaving the message thread, until the very last step (payment).
4. **Order tracking and refunds** they can ask about later, in plain language.

If the same shopper later opens the website, their cart, addresses, and orders are all already there.

---

## What shoppers can do

### Inside ChatGPT

| Flow | What it feels like |
|---|---|
| **Discover products** | Ask in natural language; ChatGPT renders a product widget with images, prices, reviews, stock. |
| **Build a cart** | "Add two of the salmon one" — items accumulate in a server-side cart that survives the conversation. |
| **Pick an address** | A saved-address picker opens in the widget; new addresses can be added inline. |
| **Confirm an order** | A summary panel shows items, totals (with US sales tax), and the chosen address. |
| **Pay** | One tap opens Stripe Checkout (card / Apple Pay / WeChat Pay / Alipay) or Coinbase Commerce (crypto). |
| **Check on orders** | "Where's my last order?" returns the live status. |
| **Request a refund** | A refund flow runs inside the widget — choose reason, submit, track status. |

### On the website

The same account, cart, and order history are reachable at https://platform.zen7.com — useful when the shopper wants a bigger screen, wants to browse without prompting, or is sharing the link with someone else.

---

## What this unlocks for the business

| Outcome | How PetPals delivers it |
|---|---|
| **Capture intent earlier** | Sell at the moment the shopper is asking *what to buy*, not after they've finished researching. |
| **Lower drop-off** | Cart, address, and confirmation all live inside the chat — fewer page loads, fewer logins, fewer abandoned carts. |
| **One identity, one funnel** | Email/password, Google sign-in, and ChatGPT OAuth all resolve to the same shopper, so analytics and CRM stay clean. |
| **Multiple payment rails** | Stripe covers cards & local wallets; Coinbase covers crypto buyers — without doubling the integration work for the merchant. |
| **Self-serve after-sales** | Refund requests are submitted, approved, and tracked through the same conversational interface, reducing support tickets. |
| **Built for AI discovery** | Site ships with sitemap, `robots.txt`, and `llms.txt` assets so the catalog is reachable by both classic search and generative engines. |

---

## Capability map

| Discover | Shop | Pay | Care |
|---|---|---|---|
| Product search | Server-side cart | Stripe Checkout | Order history |
| Rich widget cards | Saved addresses | Coinbase Commerce | Refund flow |
| Stock / price / reviews | In-widget checkout | Webhooks + reconciliation | Status sync |
| | Min-order guard | Test-account whitelist | Mall sync |

**One identity across all of it** — Email + password · Google Sign-In · ChatGPT OAuth

---

## End-to-end shopper journey

| # | Step | What happens |
|---|---|---|
| 1 | **Ask** | Shopper asks in natural language — *"find me senior cat food"* |
| 2 | **Browse** | ChatGPT renders the product widget inline |
| 3 | **Add to cart** | Items sync to a server-side cart tied to the shopper's `userId` |
| 4 | **Confirm in chat** | Pick a shipping address, see total + US sales tax in the widget |
| 5 | **Pay (external)** | Stripe / Coinbase opens; result posts back via webhook |
| 6 | **Track / refund** | *"Where's my order?"* — handled in chat or on the website |

Every step persists to the same account, so the shopper can switch between ChatGPT and the website at any point without losing state.

---

## Try it

Open PetPals in ChatGPT: [chatgpt.com/apps/petpals](https://chatgpt.com/apps/petpals/asdk_app_697047972e8c8191a13a465c9480d508), or browse on the web at [platform.zen7.com](https://platform.zen7.com).

---

## Where to go next

| If you want… | Open |
|---|---|
| The full technical reference (every endpoint, env var, ops note) | [`README.md`](./README.md) |
| The shopper-facing release checklist | `docs/release/release-checklist-pawpals.md` |
| The three core flows in depth (cart sync, identity, in-widget checkout) | `docs/CORE_FEATURES.md` |
| Payment integration details | `docs/payment-integration.md` |
| Refund / after-sales design | `docs/refund/` |
| Platform-wide service map | repo-root `CLAUDE.md` |
| Release history | [`CHANGELOG.md`](./CHANGELOG.md) |

---

Built on [Next.js](https://nextjs.org), the [OpenAI Apps SDK](https://developers.openai.com/apps-sdk), and the [Model Context Protocol](https://modelcontextprotocol.io).
