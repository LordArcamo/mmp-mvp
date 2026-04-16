# CLAUDE.md — MMP Appliances Trading Website

This file gives Claude Code the context it needs to work on this project without re-deriving it every session.

---

## Project Overview

Single-page marketing website for **MMP Appliances Trading**, an appliance store in Iligan City, Philippines. Built with Astro (static, no framework components). All sections are `.astro` components assembled in `src/pages/index.astro`.

---

## Stack & File Map

| File | Role |
|---|---|
| `src/layouts/Layout.astro` | Global CSS, design tokens, shared component styles (`.section-heading`, `.section-eyebrow`, etc.) |
| `src/pages/index.astro` | Page root — imports and orders all components |
| `src/components/Navbar.astro` | Fixed top nav, scroll-spy via IntersectionObserver |
| `src/components/Hero.astro` | Full-screen 55/45 grid — navy left panel, image right panel |
| `src/components/About.astro` | Photo composition left, text + highlight grid right |
| `src/components/Brands.astro` | Logo grid from `public/brands/*.svg` |
| `src/components/Posts.astro` | Facebook post cards from `public/posts/*.jpg` |
| `src/components/Services.astro` | Service highlight cards |
| `src/components/Contact.astro` | Google Maps iframe + store info |
| `src/components/Footer.astro` | 4-col footer, SVG wave transition from Contact |
| `public/brands/` | 8 brand SVG logos |
| `public/posts/` | 3 Facebook post images (JPGs, downloaded to avoid CDN expiry) |
| `public/favicon.svg` | MMP brand mark — navy bg, M(white) M(red) P(white) |

---

## Design Tokens (defined in `Layout.astro` `<style is:global>`)

```css
--red: #C8102E
--red-dark: #a30d25
--red-light: rgba(200,16,46,0.08)
--red-glow: rgba(200,16,46,0.3)
--navy: #0B1424
--bg: #FFFFFF
--bg-soft: #F7F8FA
--border: rgba(11,20,36,0.09)
--ink: #0B1424
--ink-mid: #3D4E63
--ink-light: #7A8899
--font-logo: 'Black Han Sans'
--font-condensed: 'Barlow Condensed'
--font-body: 'Plus Jakarta Sans'
```

### Section background order
`About → bg-soft` · `Brands → bg` · `Posts → bg-soft` · `Services → bg` · `Contact → bg` · `Footer → navy`

---

## Known Conventions

- **Class names:** Components use `.section-heading` and `.section-eyebrow` (long form). Both are aliased alongside the short-form `.sh` / `.eyebrow` in `Layout.astro`.
- **`.section-heading .red`** is the accent colour class inside headings (e.g. `<span class="red">Home to Iligan</span>`).
- **Icons:** Flaticon uicons — `fi fi-rr-*` (regular-rounded), `fi fi-sr-*` (solid-rounded), `fi fi-br-*` (brands).
- **Scroll reveal:** Elements get `class="reveal"` or `class="reveal from-left"` / `"from-right"`. An IntersectionObserver in `Layout.astro` adds `.visible` to trigger CSS transitions.
- **Navbar scroll-spy:** IntersectionObserver in `Navbar.astro` adds `.active` to the current section's nav link.

---

## Store Content

| Field | Value |
|---|---|
| Name | MMP Appliances Trading |
| Address | 1st Floor Red-C Building, Tambo Highway, Iligan City, Northern Mindanao |
| Hours | Monday – Saturday · 8AM – 6PM |
| Facebook | https://www.facebook.com/mmp.iligan |
| Financing | Billease, Tonik, Salmon, Skyro (₱0 downpayment) |
| Brands | Samsung, Haier, Midea, Panasonic, Fujidenzo, Xastron, N-Vision, dB Audio |

---

## Decisions & Fixes Applied

- `overflow: clip` on sections clips absolutely-positioned badges with negative offsets — badges in `About.astro` were repositioned to positive coordinates to avoid this.
- Hero left panel `padding-left` uses `max(2.5rem, calc((100vw - 1200px) / 2))` to align copy with the navbar's centered content edge.
- Footer wave `background` must match the Contact section (`var(--bg)`, not `var(--bg-soft)`).
- Post images are stored locally in `public/posts/` — Facebook CDN URLs expire (hex `oe=` timestamp in query string).
- `chip-zero` label must use `white-space: nowrap` — `&shy;` soft-hyphen causes a visible break in the narrow badge.
