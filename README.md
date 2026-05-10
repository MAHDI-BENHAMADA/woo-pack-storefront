# woo-pack-storefront

> Custom WooCommerce pack ordering page with dynamic pricing, Telegram notifications & Facebook Pixel tracking.

A production-ready, mobile-first e-commerce storefront built for an Algerian fashion brand. Customers can browse curated product packs, select sizes with real-time stock visibility, and complete checkout — all in a single-page experience. The store owner manages packs through a built-in admin dashboard without touching any code.

---

## ✨ Features

### Customer-Facing
- 🛍️ **Pack browsing** — visual grid of owner-created packs loaded from Firestore
- 👕 **Product carousel** — horizontal swipe carousel with live stock levels per size
- 💰 **Dynamic pricing pills** — pack prices auto-rendered from Firestore config (1–5 pieces)
- 📦 **Smart shipping** — per-wilaya home/desk delivery rates for all 58 Algerian wilayas
- 🧾 **Live order review** — itemized summary with shipping cost updated in real time
- ✅ **One-tap checkout** — order submitted directly to WooCommerce via REST API

### Admin Dashboard
- 🔐 **Firebase Auth login** — secure owner-only access
- ➕ **Pack creator** — name, image (Cloudinary upload), price tiers, best-pill badge, product picker
- ✏️ **Pack editor** — pre-populated edit form for existing packs
- 🗑️ **Pack deletion** — with confirmation prompt

### Integrations
- 📲 **Telegram notifications** — instant order alerts + incomplete order capture
- 📊 **Meta Pixel** — `Lead`, `InitiateCheckout`, and `Purchase` events
- 🖼️ **Cloudinary** — image hosting for pack thumbnails
- 🔥 **Firebase Firestore** — pack storage, real-time reads

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript |
| UI | RTL Arabic layout · Cairo & Bebas Neue fonts |
| Database | Firebase Firestore |
| Auth | Firebase Authentication |
| E-commerce | WooCommerce REST API v3 |
| Images | Cloudinary |
| Notifications | Telegram Bot API |
| Analytics | Meta (Facebook) Pixel |

---

## ⚙️ Setup

### 1. Clone the repo
```bash
git clone https://github.com/YOUR_USERNAME/woo-pack-storefront.git
cd woo-pack-storefront
```

### 2. Configure credentials

Copy the example env file and fill in your values:
```bash
cp .env.example .env
```

Then open `page-pack-order.html` and replace all `YOUR_*` placeholders near the top of the `<script>` block with your actual credentials (see `.env.example` for the full list).

| Placeholder | Where to get it |
|---|---|
| `TELEGRAM_BOT_TOKEN` | [@BotFather](https://t.me/BotFather) on Telegram |
| `TELEGRAM_CHAT_ID` | Your group/channel ID |
| `FIREBASE_API_KEY` etc. | Firebase Console → Project Settings |
| `WC_CONSUMER_KEY` / `WC_CONSUMER_SECRET` | WooCommerce → Settings → Advanced → REST API |
| `CLOUDINARY_CLOUD_NAME` / `UPLOAD_PRESET` | Cloudinary Dashboard |

### 3. Deploy

This is a standalone HTML file — host it anywhere:
- **WordPress**: paste as a custom HTML page/shortcode
- **Static hosting**: Netlify, Vercel, GitHub Pages
- **Direct**: upload `page-pack-order.html` to your server

---

## 📁 Project Structure

```
woo-pack-storefront/
├── page-pack-order.html   # Main storefront (all-in-one: CSS + HTML + JS)
├── backup.php             # WordPress plugin integration (order handler)
├── .env.example           # Credential template
├── .gitignore
└── README.md
```

---

## 🔑 Credentials

> [!CAUTION]
> **Never commit real API keys.** The `.env` file is listed in `.gitignore`. Only commit `.env.example` with placeholder values.

---

## 📸 Views

| View | Description |
|---|---|
| Pack List | Grid of available packs loaded from Firestore |
| Pack Detail | Product carousel + size picker + checkout form |
| Admin Login | Firebase Auth email/password |
| Admin Dashboard | Create, edit, delete packs |

---

## 📄 License

MIT — free to use, fork, and adapt.
