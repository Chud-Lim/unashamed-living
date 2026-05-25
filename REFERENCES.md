# REFERENCES.md — Layout & structure patterns (inspiration only)

Scraped 2026-05-25 for STRUCTURE/LAYOUT/spacing/type/gallery patterns only. No copy, logos, images, or brand assets are taken from these sites. Build to the Unashamed Living design system; these inform rhythm and composition.

## Cross-site takeaways
- **Long-form vertical page, distinct tiers.** Generous whitespace around hero + narrative/mission; tighter spacing inside product grids. Clear alternation: full-bleed cinematic → product → editorial → giving → product → capture.
- **Hero:** full-bleed image/video, text overlay (centered or bottom-left), large display type, gradient scrim for legibility. (Tecovas, Mejuri, Elevated Faith all full-bleed.)
- **Type:** serif display headlines + sans body is the premium default (Mejuri, Kotn use serif display). UL = editorial serif display + humanist sans body.
- **Palette:** neutral/warm base, restrained accents. UL leans warmer (bone/espresso/brass) than these neutrals — that is our differentiator.
- **Motion:** carousels with manual controls; subtle product-card hover state; restraint over flash.

## Homepage section rhythm (synthesized)
1. **Hero** — full-bleed, cinematic, 1 big headline + 1-2 CTAs, gradient overlay. (Tecovas "Made Right", Mejuri "Summer Guide", EF campaign.)
2. **Category tiles / Shop-the-look** — 3-up grid, on-model imagery, label + link overlay. (Mejuri 3-col.)
3. **Featured / best-sellers grid** — 4-up cards: image (front→back hover swap), title, price, badge, reviews. (EF 5-col, Mejuri trending carousel.)
4. **Mission / impact** — Kotn-style: manifesto + structured impact, dark surface. Elevated Faith validates the **3-icon pillar** pattern (prayer/heart/globe = charity mission) — matches UL's 3 pillars (fund churches / Christ in conversations / fund communities). Add 3 impact stats + CTA. Dark surface for gravity.
5. **Editorial story** — split image + copy, serif display, lots of air ("Together we represent Him"). (Kotn/Mejuri narrative blocks.)
6. **Jewelry feature** — Mejuri merchandising: macro + on-body, calm, 1 strong CTA.
7. **Testimonials / UGC** — quote stack or carousel, name attribution, text-led. (EF social proof.)
8. **Newsletter** — centered single column, spacious, headline + email input, warm minimal. (Tecovas, Kotn, EF.)

## PDP patterns (Mejuri = primary styling reference for the EXISTING product section)
- **Gallery:** LEFT vertical thumbnail rail (Mejuri 5 thumbs, Tecovas 8), large main image, **macro + on-body mix**, zoom. Calm, lots of air. → Style Horizon's existing gallery toward a left/side thumbnail rail + large main via settings + scoped CSS.
- **Buy-box order:** title → star rating → price → variant picker(s) → ATC → (trust/shipping note) → accordions. Mejuri/Tecovas both follow this. Keep Horizon's existing order; lift type/spacing/button.
- **Trust note near ATC:** Tecovas shows "Free Shipping $100+" inline. UL differentiator: a compact **giving + trust strip right after ATC** (Equips Churches · Global Impact · Fast Shipping + "10% of every sale"). Note: Elevated Faith puts giving BELOW the fold ("Our Cause"); UL pulls a short version up near ATC for stronger brand signal, full mission block lower.
- **Accordions:** Description, Materials & Fit, Shipping & Returns (Tecovas: Description/Features/Material & Care/Shipping & Returns). Keep concise.
- **Below fold:** complementary "Style With" / "Complete the look" carousel (Mejuri), then mission reinforcement, then reviews (Judge.me). 
- **Sticky info column** on desktop (Horizon already supports `sticky_details_desktop: true`).

## Notes
- AllSaints homepage returned 403 to the scraper; relying on known patterns: bold high-contrast hero, near-monochrome palette, restrained scroll motion, elevated feel in secondary sections (use as the "restraint + contrast" cue for hero + dark sections).
- Tecovas is the dominant look cue: warm earthy palette, full-bleed cinematic photography, heritage/craft rhythm, accordion-rich PDP with trust notes.
