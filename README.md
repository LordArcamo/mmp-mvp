# MMP Appliances Trading — Official Website

Marketing website for **MMP Appliances Trading**, a home appliance store located at the 1st Floor Red-C Building, Tambo Highway, Iligan City, Northern Mindanao, Philippines.

---

## Live Sections

| Section | Description |
|---|---|
| **Hero** | Full-screen brand intro with MMP mark, CTAs, and product image |
| **About** | Store overview, photo composition, and key selling points |
| **Brands** | Logo grid of all carried brands |
| **Posts** | Latest Facebook promotional posts |
| **Services** | Delivery, installment, and warranty highlights |
| **Contact** | Google Maps embed + store contact details |

---

## Stack

- **Framework:** [Astro](https://astro.build) (static site, zero JS by default)
- **Styling:** Scoped CSS per component + global tokens in `Layout.astro`
- **Icons:** [Flaticon Uicons](https://www.flaticon.com/uicons) (regular-rounded, solid-rounded, brands)
- **Fonts:** Black Han Sans · Barlow Condensed · Plus Jakarta Sans (Google Fonts)

## Brand Tokens

| Token | Value |
|---|---|
| `--red` | `#C8102E` |
| `--navy` | `#0B1424` |
| `--font-logo` | `'Black Han Sans'` |
| `--font-condensed` | `'Barlow Condensed'` |
| `--font-body` | `'Plus Jakarta Sans'` |

---

## Project Structure

```
/
├── public/
│   ├── brands/          # SVG brand logos (8 brands)
│   ├── posts/           # Facebook post images (JPG)
│   └── favicon.svg      # MMP brand mark favicon
├── src/
│   ├── layouts/
│   │   └── Layout.astro # Global styles, design tokens, fonts
│   ├── components/
│   │   ├── Navbar.astro
│   │   ├── Hero.astro
│   │   ├── About.astro
│   │   ├── Brands.astro
│   │   ├── Posts.astro
│   │   ├── Services.astro
│   │   ├── Contact.astro
│   │   └── Footer.astro
│   └── pages/
│       └── index.astro  # Single-page site
├── astro.config.mjs
└── package.json
```

---

## Getting Started

**Requirements:** Node.js ≥ 22.12.0

```bash
# Install dependencies
npm install

# Start dev server at localhost:4321
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

---

## Store Info

| | |
|---|---|
| **Address** | 1st Floor Red-C Building, Tambo Highway, Iligan City |
| **Hours** | Monday – Saturday · 8AM – 6PM |
| **Facebook** | [facebook.com/mmp.iligan](https://www.facebook.com/mmp.iligan) |
| **Financing** | Billease · Tonik · Salmon · Skyro (₱0 downpayment) |

## Brands Carried

Samsung · Haier · Midea · Panasonic · Fujidenzo · Xastron · N-Vision · dB Audio
