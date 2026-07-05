# kiln-site

Public marketing site for **Kiln** — served via GitHub Pages.

This repository is intentionally **public** and contains **only** the landing page.
It holds no source code, no docs, and nothing about how Kiln is built. The Kiln
codebase itself lives in a **separate private repository**.

## Publishing (GitHub Pages)

1. Create a **public** repo named `kiln-site` and push this folder to it.
2. In the repo: **Settings → Pages → Build and deployment**
   - **Source:** *Deploy from a branch*
   - **Branch:** `main` / `/ (root)`
3. The site goes live at `https://<user>.github.io/kiln-site/` within a minute or two.

`.nojekyll` is included so GitHub serves the files as-is (no Jekyll processing).

### Optional: custom domain
Add a `CNAME` file containing your domain and configure DNS per GitHub's docs.

## Pages

- `index.html` — the marketing landing page.
- `order.html` — the customer order flow (beta-agreement gate → configure model + data
  → live cost estimate → submit). Linked from the landing page's "Order a model" CTAs.

## Order flow — going live

`order.html` is a **static** page (GitHub Pages can't run a backend), so it's wired to
work with **zero backend by default** and upgrade when you're ready. All the knobs live
in the `CONFIG` block at the top of the `<script>` in `order.html`:

- **`PRICING`** — ⚠️ **edit these numbers before real orders.** They're illustrative
  beta figures. The page shows the estimate as a ±20% range.
- **Submitting the order** — by default the Submit button opens the customer's email app
  pre-filled with their full order to `gao.skyler@icloud.com` (no signup needed). For
  nicer capture (and file attachments), set **`FORM_ENDPOINT`** to a
  [Formspree](https://formspree.io) / Getform / Basin URL.
- **Prepayment** — a static page can't charge cards. Leave **`PAYMENT_LINK`** empty and
  the customer is told you'll email a payment link after review (recommended for variable
  pricing). Or paste a [Stripe Payment Link](https://stripe.com/payments/payment-links) /
  Gumroad URL and an instant "Prepay deposit" button appears on the confirmation screen.

The beta disclaimer (turnaround of weeks–months, estimate-not-final, no accuracy
guarantee) gates the whole form: nothing is fillable until the customer ticks agree.

`order.html` is set `noindex` so search engines skip it while you're in beta.

## License
© 2026 Kiln. All rights reserved. This content is not licensed for reuse.
