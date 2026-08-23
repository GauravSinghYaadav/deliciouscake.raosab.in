# Delicious Cakes By Rao_sab — Website

An advanced single-page website for your cake business — 20 cake designs,
occasion filters, WhatsApp ordering, UPI "Buy Now" links, live order-status
badge, and a quick-view popup for each cake.

## Folder structure

```
delicious-cakes/
├── index.html                     ← the whole site (HTML + CSS + JS in one file)
├── README.md
└── assets/
    └── images/
        ├── logo/
        │     logo.png             ← your shop logo (used in navbar, hero, footer)
        │     logo-256.png         ← small version (used as browser tab icon)
        ├── hero/                  ← background slideshow (6 images)
        │     hero-1.jpg ... hero-6.jpg
        └── cakes/                 ← 20 cake photos
              cake-01.jpg ... cake-20.jpg
```

**A logo and placeholder photos are already included** so the site looks
complete right now. Swap them for your real photos later — just keep the
**same file names** (e.g. save your real photo of cake #1 over `cake-01.jpg`)
and the site updates automatically, no code changes needed.

- Logo: square, transparent or white background works best, ~900×900px.
- Hero images: landscape, ~1920×1080px (4K-style wide shots of your bakery/cakes).
- Cake photos: square, ~1000×1000px.

Want a different logo design entirely (a hand-drawn or professionally
designed one instead of the generated badge)? Just ask and I can generate
alternative styles, or you can drop in a designer's file using the same
filename.

## Before you go live — 3 things to edit

Open `index.html`, find the `CONFIG` block near the top of the `<script>`
section, and update:

```js
const CONFIG = {
  whatsappNumber: "919999999999",   // ← your real WhatsApp number
                                     //   format: countrycode + number, no + no spaces
                                     //   e.g. "919812345678"

  upiId: "raosabcakes@upi",         // ← your real UPI ID (VPA)
                                     //   e.g. "yourname@okaxis" or "raosab@ybl"
  upiPayeeName: "Delicious Cakes By Rao_sab",

  orderOpenHour: 6,                 // 6 AM
  orderCloseHour: 18                // 6 PM
};
```

**About "Buy Now" (UPI):** tapping it opens `upi://pay?...`, which launches
GPay / PhonePe / Paytm **on a phone** with the amount pre-filled — this is
how you collect the 100% advance payment before confirming an order. UPI
links don't open a payment app on desktop browsers; that's a UPI limitation,
not a bug. If you'd also like a scannable QR code for desktop visitors,
generate one free at `upiqr.in` using your UPI ID, save it as
`assets/images/upi-qr.png`, and I can wire it into the "Buy Now" flow as a
popup.

## What's built in

- **20 cake designs** — each with photo, flavour badge, occasion tags,
  price (₹ / 1 Kg), an **Inquire Now** button (opens WhatsApp with the cake
  name + price pre-filled) and a **Buy Now** button (opens a UPI payment
  request for that price).
- **Occasion filters** — Birthday / Anniversary / Celebration / Achievement —
  tap a chip to instantly filter the grid (a cake can belong to more than
  one occasion).
- **Quick-view popup** — click any cake photo to see a larger view with the
  same order buttons.
- **Live order-status badge** in the hero — automatically shows "Ordering
  Open" or "Ordering Closed" based on the visitor's own device clock and
  your configured 6 AM–6 PM window.
- **Delivery-policy strip** — states the 6 AM–6 PM order window, 3-hour
  delivery, next-day delivery after 6 PM, and advance UPI payment
  requirement, prominently near the top and again in the footer.
- **Sticky navigation bar** with your logo that appears on scroll.
- **Rotating 4K-style hero background** — 6 images crossfade with a slow
  zoom; respects visitors' "reduce motion" accessibility setting.
- **Floating WhatsApp button** visible on every scroll position.
- Scroll-reveal animations on the cake cards, fully responsive down to
  small mobile widths.

## Publish the site (GitHub Pages, or any host)

1. Create a GitHub repository and upload everything inside this
   `delicious-cakes/` folder to the **root** of that repo (`index.html`
   should sit directly in the repo, not inside a subfolder).
2. In the repo: **Settings → Pages → Build and deployment → Source** =
   "Deploy from a branch", branch = `main`, folder = `/ (root)`. Save.
3. If you later buy a domain, add a `CNAME` file containing just the domain
   name (e.g. `deliciouscakesbyraosab.com`) to the repo root, set it in
   **Settings → Pages → Custom domain**, and point your domain's DNS A
   records to GitHub Pages: `185.199.108.153`, `185.199.109.153`,
   `185.199.110.153`, `185.199.111.153`.

## Suggestions for later

- Add a short "About Rao_sab" story section — customers love knowing who
  bakes their cake.
- Add customer photos/reviews once you have a few happy orders.
- Add cake size options (0.5 Kg / 1 Kg / 2 Kg) with adjustable pricing —
  I can wire this into the cards and UPI links when you're ready.
- If order volume grows, a proper checkout with a payment gateway
  (Razorpay/Instamojo) plus order tracking will scale better than manual
  UPI links + WhatsApp — happy to help set that up.
