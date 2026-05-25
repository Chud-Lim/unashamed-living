# PROGRESS — Unashamed Living homepage + PDP premium redesign

## Status: SHIPPED to the unpublished theme ✅

- **Store:** `unashamed-living.myshopify.com`
- **Deployed theme (unpublished):** `unashamed-living/master` `#158941053151`
- **Live theme (untouched):** `Fabric` `#154435223775`
- **Preview:** https://unashamed-living.myshopify.com/?preview_theme_id=158941053151 (add `&pb=0` to hide the preview bar)

### How it deployed
The target theme is **GitHub-connected** to this repo's `master`. Running `shopify theme dev --theme 158941053151` synced the local build straight to that theme, which auto-committed it back to `master` ("Update from Shopify…"). So the redesign is on **both** the unpublished theme and `master`. No live theme was touched; nothing was published.

## What shipped

### Foundation (shared)
- `snippets/ul-tokens.liquid` — brand design tokens (palette, fonts, spacing scale, JS-free scroll-reveal) emitted as CSS custom properties, rendered by every `ul-` section.
- `config/settings_schema.json` — additive **"Unashamed Living Brand"** group: 5 colors (bone/espresso/dark/brass/oxblood) + 2 `font_picker`s (display serif, body sans). All admin-editable.

### Homepage — `templates/index.json` (8 sections, all `ul-`)
1. `ul-hero` — full-bleed cinematic hero, separate desktop/mobile `<picture>`, eyebrow/heading/subheading/2 CTAs as blocks.
2. `ul-category-tiles` — 3 image tiles (Apparel / Accessories / Home Decor), pull collection imagery, mobile carousel.
3. `ul-featured-collection` — best-sellers grid, hover image-swap cards, sale badges (wired to `frontpage`).
4. `ul-mission-impact` — dark giving block: manifesto + 3 brass stats + CTA + lifestyle image.
5. `ul-editorial-story` — split image + copy ("Together we represent Him").
6. `ul-jewelry-feature` — Mejuri-style jewelry row (pendant / ring / pin).
7. `ul-testimonials` — 3 community quotes, brass quote marks, star ratings.
8. `ul-newsletter` — email capture over atmospheric image (real `{% form 'customer' %}`).

### Product page — `templates/product.json` (existing buy-box kept intact)
- **Kept** the theme's `product-information` section — gallery, variant picker, ATC, sticky bar all unchanged. Variant switching verified working.
- Added `blocks/ul-giving.liquid` (giving + trust strip) right after the buy buttons.
- Added a **Shipping & Returns** accordion row.
- `sections/ul-pdp-overrides.liquid` — light, scoped (`.product-information`) brand styling: Playfair title/accordion headers, brass ATC, oxblood sale price, refined swatches/spacing.
- `ul-product-complementary` — "Complete the look" carousel (wired to `frontpage`, excludes current product).
- Compact `ul-mission-impact` — dark giving reinforcement band.
- Kept the existing prayer block and Judge.me reviews.

## QA (live, via theme dev)
- Verified at **375 / (768) / 1440** on homepage + a product page.
- **0 horizontal overflow** at 375 (home + PDP). Mobile uses hamburger nav + carousels; desktop sticky buy box.
- Variant switching updates the `?variant=` URL correctly; ATC styled brass.
- **`shopify theme check`: 0 offenses on all new/edited files.** No Liquid or console errors from theme code.

## Manual TODOs / things to confirm in admin
- **Fonts:** defaults are **Playfair Display** (display) + **Work Sans** (body). Confirm or swap in *Theme settings → Unashamed Living Brand*. Colors are editable in the same group.
- **Best-sellers:** the featured grid is wired to the `frontpage` collection. If you want a curated best-sellers set, create/curate a collection and select it on the *UL Featured* section.
- **Category "Accessories" tile:** it auto-pulls the `accessories` collection's first product image (currently a cap). To show a jewelry piece specifically, set that tile's image in the *UL Categories* section, or create a dedicated Jewelry collection. (Labeled "Accessories" rather than "Jewelry" to match the actual imagery/link.)
- **Complementary products:** wired to `frontpage` excluding the current product; set a curated "styled together" collection on *UL Complete Look* if preferred.
- **Newsletter** submits to your Shopify customer list with the `newsletter` tag.
- **Lifestyle imagery** uses existing `freepik__*` store Files as editable defaults (distinct per page — no image reused 3×). Swap any via each section's image settings.

## Known non-issues
- `theme check` reports `JSONMissingBlock` for the **Judge.me** and **Kiwi size-chart** app blocks in `product.json`. These are **pre-existing app blocks** (also present in `collection.json`, `product.subscription.json`, etc.); the app injects them at runtime. Not introduced by this work and not removable without dropping that app functionality.
- Shop-login CSP console errors appear **only on the localhost dev server** (the dev origin can't frame `shop.app`); they do not occur on the real preview URL.
