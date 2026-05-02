# 🛒 Kirana

> *Your kirana store uncle knew you'd run out of milk before you did. Now your Kirana AI Agent does too.*

Kirana is an AI agent that lives in your WhatsApp (or Telegram). It learns your grocery consumption patterns from your Swiggy Instamart order history and automatically restocks your pantry — before you run out.

No app to open. No list to maintain. Just groceries that show up when they should.

---

## How it works

Kirana runs quietly in the background. Every day it:

1. **Pulls** your Instamart order history via the Swiggy MCP API
2. **Models** per-item consumption rate — *"you buy 1L milk every ~5 days"*
3. **Infers** what's likely depleted based on days since last purchase
4. **Messages you** on WhatsApp/Telegram with a draft restock cart to review
5. **Checks out** on Instamart the moment you say *"yes"* — best coupon applied automatically

```
Kirana: Hey! Looks like you're running low on milk, eggs, and bread.
        Restock cart ready — ₹284 total (coupon INSTA20 applied).
        Should I place the order?

You:    Yes

Kirana: ✅ Order placed. Arriving in 15 minutes.
```

---

## Why

Most grocery apps show you what you ordered. Kirana tells you what you *need*. The intelligence lives in the pattern — not in you remembering to open an app.

---

## MCP tools used

| Server     | Tool                  | Purpose                              |
|------------|-----------------------|--------------------------------------|
| Instamart  | `get_orders`          | Pull order history                   |
| Instamart  | `your_go_to_items`    | Seed initial item list               |
| Instamart  | `search_products`     | Resolve item → product ID + variants |
| Instamart  | `update_cart`         | Build restock cart                   |
| Instamart  | `get_cart`            | Verify cart before checkout          |
| Instamart  | `checkout`            | Place order                          |

---

## Built on

This project is part of the **[Swiggy Builders Club](https://mcp.swiggy.com/builders/)** — Swiggy's MCP platform open to developers and startups building AI-powered products on top of Food, Instamart, and Dineout.

---

## Status

🚧 Early development. Watch this space.

---

## License

MIT
