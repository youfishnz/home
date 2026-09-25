# YouFishNZ website — RCTF spec

## Role

You are a senior front-end engineer who cares about accessibility and plain, maintainable code. You are building a small static marketing site for a one-person business, and the owner will maintain it by hand without developer help.

## Context

- **The business.** YouFishNZ is a tropical fish breeder in New Zealand. It specialises in angelfish colour morphs and also sells livebearers and live food cultures. Most visitors are local aquarists on phones. They want to see what is available and then get in touch by email, WhatsApp or Trade Me.
- **The current site** is one `index.html` page that pulls in Tailwind and Google Fonts from the internet. It is being replaced by a self-contained page with the same content, a cleaner build and better accessibility.
- **Where it runs.** It is served by a static host (GitHub Pages) from a sub-folder, and the owner also opens it straight from disk to check changes. There is no build step. The page sits in the same folder as its images.
- **Images in the folder:**

  | File | Size (px) | What it shows |
  |---|---|---|
  | `logo.png` | 400 × 197 | Blue fish logo with "YOUFISH NZ" lettering, on a transparent background |
  | `angelfish-philippine-blue.png` | 1376 × 768 | Philippine Blue Silver, Platinum and Ghost angelfish in a tank |
  | `angelfish-pinoy-black.png` | 1376 × 768 | Pinoy and Black angelfish in a tank |
  | `angelfish-bulgarian-seal-point-green.png` | 1376 × 752 | Bulgarian Seal Point and Green angelfish in a tank |

- **Visitors include people with colour-vision deficiency**, so state and emphasis should never rely on colour alone.

## Task

Build one self-contained HTML page for the site, using the content, look and behaviour described below.

### 1. Page content

Use this text as written. It is the current site's copy, with New Zealand spelling applied.

**Page title:** YouFishNZ | Tropical Fish Breeder New Zealand
**Meta description:** YouFishNZ – Specialty tropical fish breeder in New Zealand. Philippine Blue, Pinoy, Black, Bulgarian Green & Seal Point angelfish, guppies, swordtails and live micro worms.

**Header**
- Logo, linking back to the top of the page
- Navigation: About · Livestock · Contact
- A "Contact" button

**Hero**
- Small label: New Zealand Tropical Fish Breeder
- Main heading, on two lines: "Healthy, locally bred" / "tropical fish" (the second line is highlighted)
- Paragraph: Specialty angelfish, livebearers and live foods raised with care in New Zealand. Quality genetics, strong fish, ready for your aquarium.
- Buttons: "View Livestock" (goes to Livestock) and "Get in Touch" (goes to Contact)

**About — heading "About YouFishNZ"**
1. Kia ora! I'm a dedicated tropical fish breeder based in New Zealand, focused on producing healthy, high-quality freshwater fish for local aquarists.
2. My specialty is angelfish colour morphs — particularly the sought-after Philippine Blue lines, Pinoy, Black, Bulgarian Green and Bulgarian Seal Point. I also breed popular livebearers and culture live foods to give your fish the best start.
3. All fish are raised in carefully maintained systems with attention to genetics, health and temperament. Whether you're looking for show-quality angelfish or hardy community fish, I'm happy to help.

Four feature tiles:

| Icon | Title | Subtitle |
|---|---|---|
| 🐟 | Angelfish | Specialty morphs |
| 🌊 | NZ Based | Local breeding |
| 🧬 | Quality Genetics | Selected lines |
| 🪱 | Live Foods | Micro worms |

**Livestock — heading "Current Livestock"**
Intro: Available fish and live foods. Stock changes regularly — message me for current availability, sizes and pricing.

Group heading: Angelfish (*Pterophyllum scalare*). Three photo cards:

| Photo | Title | Subtitle | Description | Varieties |
|---|---|---|---|---|
| `angelfish-philippine-blue.png` | Philippine Blue Angelfish | Silver, Blue Platinum & Ghost | Stunning structural blue iridescence that shifts beautifully under aquarium lighting. Includes Philippine Blue Silver, Blue Platinum, and Ghost varieties. | Philippine Blue Silver · Philippine Blue Platinum · Philippine Blue Ghost |
| `angelfish-pinoy-black.png` | Pinoy & Black Angelfish | Dark body morphs & metallic tones | Deep, dark pigmentation with high-contrast characteristics. Pinoy features dark bodies overlaid with intense blue metallic sheen alongside classic solid dark lines. | Pinoy Angelfish · Black Angelfish |
| `angelfish-bulgarian-seal-point-green.png` | Bulgarian Seal Point & Green | Specialty Bulgarian genetics | Rare genetic lines featuring distinct colourations ranging from metallic green hues to dark point patterns on a light body. | Bulgarian Seal Point Angelfish · Bulgarian Green Angelfish |

Group heading: Livebearers & Live Food. Three icon cards:

| Icon | Title | Label | Description |
|---|---|---|---|
| 🐠 | Guppies | Livebearer | Colourful, active and hardy. Perfect for community tanks or as a reliable livebearer project. |
| 🗡️ | Swordtails | Livebearer | Classic *Xiphophorus* with the iconic swordtail. Active mid-water swimmers that add movement and colour. |
| 🪱 | Micro Worms | Live food culture | Excellent first food for fry and small fish. Easy to culture and highly nutritious. Available as starter cultures. |

**Contact — heading "Get in Touch"**
Intro: Interested in any of the fish above or want to know current availability and prices? Send me a message — happy to help with advice too.

| Icon | Label | Shows | Links to |
|---|---|---|---|
| 📧 | Email | youfishnz@gmail.com | an email link (see *Email address* under Behaviour) |
| 💬 | WhatsApp | +64 210 288 4292 | https://wa.me/642102884292 (new tab) |
| 🛒 | Trade Me | View my listings | https://www.trademe.co.nz/a/search?member_listing=9300362 (new tab) |

Note below the tiles: Pickup or local delivery preferred. Shipping can be arranged for hardy species depending on location and weather.

**Footer:** logo, and "© 2026 YouFishNZ · Tropical Fish Breeder · New Zealand".

### 2. Look and feel

The feel is a clean "ocean" theme: deep navy and teal bands framing light content sections, rounded cards, soft shadows and generous spacing.

- **Page rhythm, top to bottom:** a light header; a dark hero band; a white About section; a light-grey Livestock section with white cards; a dark Contact band; a dark footer.
- **Dark bands** (hero and contact) look the same in both themes. The hero is a diagonal gradient from deep navy through ocean blue to dark teal, with two large, soft, blurred glows for depth. The text is white, and "tropical fish" is in a light aqua. Keep the glows faint so the text over them stays readable.
- **Logo.** The artwork is blue on a transparent background, which is hard to see on dark colours. Place it on a small white rounded plate wherever it appears.
- **Typography:** the device's system font stack. Headings are heavy (weight 700–800). The hero heading scales from about 2.25rem on phones to about 4rem on desktop.
- **Content width:** about 72rem at most, centred, with comfortable side padding on phones.
- **Photo cards:** a 16:9 photo at the top, cropped to fill. A small "Enlarge" chip with an icon sits over the corner of the photo. Below it come the title, subtitle and description, and then the varieties in a tinted, bordered box with small diamond markers. The card lifts slightly on hover.
- **Icon cards:** a colourful gradient band with the large emoji (warm orange for guppies, amber for swordtails, green for micro worms), then the title, the label as an outlined pill, and the description. These colours are decoration only.
- **Contact tiles:** translucent panels on the dark band, each with a round icon badge, a bold label and the value. The whole WhatsApp and Trade Me tiles are clickable. The delivery note sits in a panel with a thick left border.
- **Suggested palette** (every text pair below passes WCAG AA):

  | Role | Light theme | Dark theme |
  |---|---|---|
  | Page background | `#f8fafc` | `#0b1220` |
  | Card / header surface | `#ffffff` | `#111a2e` |
  | Tinted surface | `#f0f9ff` | `#0f2438` |
  | Body text | `#0f172a` | `#e2e8f0` |
  | Muted text | `#475569` | `#a8b3c4` |
  | Headings | `#0c4a6e` | `#bae6fd` |
  | Links and main button | `#0369a1` (white text) | `#7dd3fc` (navy text) |
  | Borders | `#cbd5e1` | `#2a3a55` |

  | Dark bands (both themes) | Value |
  |---|---|
  | Hero gradient | `#082f49` → `#0c4a6e` → `#115e59` |
  | Contact gradient | `#082f49` → `#0c4a6e` |
  | Text / muted text / accent | `#ffffff` / `#cfe3f1` / `#5eead4` |
  | Hero main button | `#2dd4bf` with `#062a3f` text |

### 3. Behaviour

- **Header.** It stays at the top while scrolling. Once the visitor scrolls, it becomes a little shorter, the logo shrinks slightly and a shadow appears. It holds the navigation links, a light/dark theme button and the Contact button.
- **Mobile menu.** Below about 768px wide, the links fold behind a menu button. The button tells screen readers whether the menu is open. The menu closes when a link is chosen, when Escape is pressed (focus goes back to the button), when the visitor clicks outside it, and when the window widens to desktop size. If JavaScript is off, the links stay visible instead.
- **In-page links** scroll smoothly, unless the visitor prefers reduced motion. The target heading is never hidden under the sticky header.
- **Current section.** The nav link for the section in view is highlighted with heavier text and a solid bar, not by colour alone. At the bottom of the page, Contact is highlighted.
- **Photo viewer.** Clicking an angelfish photo, or pressing Enter/Space on it, opens it large on a dark backdrop with its title and subtitle as a caption. It closes with a visible Close button, Escape, or a click outside the photo. Keyboard focus stays inside the viewer while it is open and returns to the photo afterwards. The page behind doesn't scroll. The viewer shows the same image file as the card, since there is no separate large version.
- **Reveal on scroll.** Cards fade and rise gently into view as the visitor scrolls. This is skipped for visitors who prefer reduced motion. Content is never left invisible if the animation can't run, for example when printing or when a card receives keyboard focus.
- **Theme.** The page follows the device's light or dark setting. The theme button switches for the current visit only, and a reload returns to the device setting. The button shows the current state with a sun or moon icon and exposes a pressed state to screen readers.
- **Missing images.** If an image file is missing, show a neutral grey placeholder that says "Image missing" and names the expected file. This tells the owner exactly what to upload. It should work even when an image fails before the rest of the page has finished loading.
- **Email address.** Build the address with a script so simple scrapers can't read it from the page source, and keep the plain address out of the structured data too. Without JavaScript, show it as "youfishnz [at] gmail [dot] com".

### 4. Technical expectations

- **Self-contained.** One HTML file with its CSS and JavaScript inline, in plain JavaScript with no frameworks. It makes no external requests: no CDNs, web fonts, libraries or analytics. It works when opened from disk and when served from a sub-folder.
- **Paths.** Reference images by bare file name, relative to the page, e.g. `logo.png`. Other internal references are relative or in-page anchors. The only full URLs are the WhatsApp and Trade Me links and `og:image`.
- **Images** carry their real width and height. Lazy-load the photos and the footer logo; the header logo loads normally because it is visible straight away.
- **Nothing is stored** in the browser (no localStorage, sessionStorage or cookies), and the page makes no network calls of its own.
- **Icons** are emoji or inline SVG. The favicon is an inline SVG, so there is no extra file.
- **Accessibility (WCAG 2.1 AA):**
  - header, nav, main, section and footer landmarks
  - one `h1` and a logical heading order
  - a skip-to-content link
  - focus rings that are visible in both themes and on the dark bands
  - descriptive alt text
  - 4.5:1 text contrast, including text over gradients
  - tap targets of at least 44px
  - motion reduced when the visitor asks for it
  - links that open a new tab say so to screen readers
- **SEO and sharing:**
  - the title and meta description above
  - Open Graph and Twitter card tags, with `og:image` set to the full URL `https://youfishnz.github.io/home/logo.png`
  - a canonical link using a relative path
  - a JSON-LD `LocalBusiness` block with name, description, telephone, country (NZ) and the Trade Me listing as `sameAs`
- **Language:** `lang="en-NZ"`, with New Zealand spelling in all visible text.
- **Editability.** Label the CSS, JavaScript and HTML with clear section comments so the owner can find and change text, stock lines and prices. Near the livestock cards, add a short comment explaining how to add or remove a variety, add a price to a variety line, and replace a photo.

### 5. Out of scope

Build tooling, service workers, analytics, contact forms, e-commerce and any runtime network request.

## Format

Reply in this order, keeping commentary outside these sections to a minimum:

1. **Assumptions and decisions:** up to 10 short points covering anything you inferred rather than were told.
2. **The file:** the complete HTML, top to bottom, with nothing elided. Save it in the current working directory, the same folder as the images, as `yfnz_<model-name>.html`, where `<model-name>` is the name of the model that generated it (e.g. `yfnz_model1.html`). Use a relative path and replace any existing file with the same name.
3. **Deployment checklist:** the folder listing the owner should have (the HTML plus the four images).
4. **Verification steps:** numbered browser checks, including opening the file from disk, loading it from a sub-folder on a static host, confirming in DevTools → Network that there are no third-party requests, and confirming that no image returns a 404.
5. **Risk and change summary:** a table with the columns Change | Rationale | Risk | Mitigation.
