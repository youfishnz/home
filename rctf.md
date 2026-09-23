# RCTF — Revised Concrete Framework (YouFishNZ)

## 1. SCOPE & OBJECTIVES

### Primary Objective
Produce a single, self-contained `index.html` file that replaces the current YouFishNZ marketing site at https://youfishnz.github.io/home/ and will be deployed to GitHub Pages under `/home/index.html`.

### Secondary Objectives
- Zero external dependencies (no CDN links, no webfonts, no libraries).
- WCAG 2.1 AA compliance across all interactive elements.
- Full responsiveness from 320 px mobile to 1920 px desktop.
- Light/dark theme toggle with session-only persistence.

## 2. CONTENT INVENTORY (verbatim copy)

### Header
- Logo → links to `#home`
- Nav: About / Livestock / Contact
- Contact CTA button

### Hero Section
- Eyrow: "New Zealand Tropical Fish Breeder"
- H1: "Healthy, locally bred tropical fish"
- Paragraph: specialty angelfish, livebearers and live foods description
- Buttons: "View Livestock" (`#livestock`) / "Get in Touch" (`#contact`)

### About Section
First-person intro opening with "Kia ora!" covering:
- Angelfish colour morphs (Philippine Blue lines, Pinoy, Black, Bulgarian Green, Bulgarian Seal Point)
- Livebearers and live foods
- Husbandry approach

Feature tiles: Angelfish / NZ Based / Quality Genetics / Live Foods

### Livestock Section
Intro line: stock changes regularly, message for availability/sizes/pricing.

**Angelfish (Pterophyllum scalare)** — three photo cards:
1. Philippine Blue Angelfish — "Silver, Blue Platinum & Ghost" + structural blue iridescence description + bullet list of three varieties.
2. Pinoy & Black Angelfish — "Dark body morphs & metallic tones" + description + bullet list of two varieties.
3. Bulgarian Seal Point & Green — "Specialty Bulgarian genetics" + description + bullet list of two varieties.

**Livebearers & Live Food** — three icon cards: Guppies (livebearer), Swordtails (livebearer), Micro Worms (live food culture) with descriptive copy.

### Contact Section
Intro line, three tiles:
- Email: youfishnz@gmail.com
- WhatsApp: +64 210 288 4292 → https://wa.me/642102884292
- Trade Me listings → https://www.trademe.co.nz/a/search?member_listing=9300362

Note about pickup/local delivery preferred and shipping arranged for hardy species.

### Footer
Logo + "© 2026 YouFishNZ · Tropical Fish Breeder · New Zealand"

## 3. HARD CONSTRAINTS

1. **Single file:** Exactly one `.html`. Images are the only permitted sibling files. Must work from `file://`, GitHub Pages subpath, or any static host.
2. **Vanilla JS only.** No frameworks, libraries, polyfills fetched at runtime.
3. **Inline CSS + JS:** All styles in a single `<style>` block; all scripts in a single `<script>` block. No external resources whatsoever — no `<link rel>`, no `@import`, no `<img src="data:">` for non-image content, no webfonts.
4. **No persistence:** No localStorage, sessionStorage, IndexedDB, cookies, or any network request (`fetch`/XHR).
5. **Image references:** BARE RELATIVE FILENAME only — no leading slash, no `./`, no absolute URL, no base64. Exact filenames:
   - `logo.png`
   - `angelfish-philippine-blue.png`
   - `angelfish-pinoy-black.png`
   - `angelfish-bulgarian-seal-point-green.png`
   
   Every `<img>` requires explicit width/height, loading="lazy", decoding="async" (below fold), and an onerror handler that swaps a failed image for an inline-SVG placeholder showing the expected filename.
6. **Icons:** Inline SVG or Unicode emoji only.
7. **Typography:** System font stack only (-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, ...). No webfonts.
8. **Subpath survival:** Every internal reference (anchors, favicon, images, canonical) must survive being served from a subpath. Assume no `<base>` tag.

## 4. FUNCTIONAL REQUIREMENTS

- Responsive from 320 px to 1920 px+. Mobile-first CSS.
- Sticky header that condenses on scroll; hamburger menu below ~768 px with correct aria-expanded handling, close-on-link-click, close-on-Escape, close-on-outside-click.
- Smooth in-page anchor scrolling with scroll offset for the sticky header, respecting prefers-reduced-motion.
- Scroll-spy: highlight nav item for section currently in view via IntersectionObserver.
- Livestock photo cards open a lightweight lightbox (no library): click/Enter opens, Escape/backdrop closes, focus trapped while open and restored on close. Lightbox loads the same relative filename — no separate hi-res asset.
- Reveal-on-scroll animation for cards via IntersectionObserver, disabled under prefers-reduced-motion.
- All state is in-memory JS only. Nothing persists between page loads.

## 5. QUALITY REQUIREMENTS

- **WCAG 2.1 AA:** Semantic landmarks (header`/nav`/`main`/`section`/footer), one h1, logical heading order, visible focus rings, descriptive alt text, 4.5:1 minimum contrast, skip-to-content link, 44 px minimum tap targets.
- **No hue-dependent meaning:** Use shading, weight, borders, icons or text labels for state and emphasis. Assume a colour-vision-deficient viewer.
- **Theme toggle:** Light/dark via CSS custom properties, defaulting to prefers-color-scheme with an in-page toggle. Session-only — no storage permitted.
- **SEO:** `<title>`, meta description (reuse existing), Open Graph and Twitter card tags (note: og:image REQUIRES absolute URL — hard-code https://youfishnz.github.io/home/logo.png there, flag as the one absolute reference). Canonical link to https://youfishnz.github.io/home/. Inline JSON-LD LocalBusiness`/Organization` block with contact details.
- **Inline SVG favicon** via data: URI (avoids second file request and path problems).
- **Language:** `<html lang="en-NZ">`. New Zealand English spelling throughout visible copy (colour, specialise, etc.).
- **Email obfuscation:** JS assembly at runtime against scrapers, with a `<noscript>` fallback showing a usable address.
- **Comments:** Clear sections in CSS and JS so a non-developer can find and edit copy, prices and stock lines.

## 6. OUT OF SCOPE

Build tooling, service workers, analytics, forms that POST anywhere, contact form submission, e-commerce, and any runtime network request.

## 7. OUTPUT FORMAT

Respond in this order:

1. **Assumptions & decisions** — bullet list, max 10 items. Include anything you inferred rather than were told.
2. **The file** — the complete index.html in a single fenced code block, top to bottom, no elisions, no "…rest unchanged". It must be copy-paste-runnable as-is. **Save this file to `yfnx_<model-name>.html`** where `<model-name>` is the name of the model that generated it (e.g., `yfnx_model1.html`). The HTML file must reside in the current working directory (`/home/nemo/Desktop/yfnz`) and always override any existing file with the same name.
3. **Deployment checklist** — the exact directory listing the owner must have in the repo (HTML plus the four image filenames), and any rename required from the current filenames.
4. **Verification steps** — numbered list of manual checks the owner can run in a browser, including: file:// load, GitHub Pages subpath load, DevTools → Network filtered to third-party domains showing zero requests, and confirming no 404s on image paths.
5. **Risk / change summary** — table with columns: Change | Rationale | Risk | Mitigation.

Do not include prose commentary outside these five sections.