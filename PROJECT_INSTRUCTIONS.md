# Live Free Jet Ski Website — Claude Project Brief

**Last reviewed:** June 1, 2026

**Rebrand note:** The business was renamed **NH Jet Fun → Live Free Jet Ski** and the site moved to **livefreejetski.com**. The GitHub repo was renamed to match. Old nhjetfun.com URLs 301-redirect to the new domain. The booking subdomain is still **bookings.nhjetfun.com** (not yet migrated).

**Purpose:** Durable, accurate context for Claude. Stable facts only — not a change log. Git is the source of truth for what changed when.

---

## 1. What this is

LiveFreeJetSki.com is a **5-page static marketing site** for Live Free Jet Ski (formerly NH Jet Fun), a weekly Sea-Doo jet ski rental business in Hampstead, NH. Booking is offloaded to a separate Booqable instance on a subdomain — the marketing site does not handle reservations, payments, or customer data.

- **Live site:** https://livefreejetski.com (old nhjetfun.com and www.nhjetfun.com 301-redirect here via the repo's `_redirects` file)
- **Booking system:** https://bookings.nhjetfun.com (Booqable, separate from this codebase — still on the old domain, not migrated)
- **GitHub repo:** https://github.com/beandm15/livefreejetski.com (public, `main` branch) — renamed from nhjetfun.com on Jun 1, 2026; the old repo URL still works via GitHub's automatic redirect
- **Hosting:** Netlify, auto-deploy from GitHub `main`. (Netlify project/site name may still be `nhjetfun` — the GitHub rename does not rename the Netlify site. Verify in the dashboard; the repo rename can break Netlify's webhook and stall auto-deploys — see §2.)
- **DNS / domain:** Namecheap, nameservers pointed at Netlify
- **Business email:** info@livefreejetski.com (was bookings@nhjetfun.com)
- **Legal entity:** Veralase LLC d/b/a Live Free Jet Ski (referenced in footer, About section, JSON-LD, and rental agreement — **do not strip**)
- **Owner:** David Bean (GitHub: beandm15)

---

## 2. Tech & deployment

Pure static site — **no build step, no framework, no package manager**. Every page is hand-edited HTML with inline `<style>` and small inline `<script>` blocks. Each page is fully self-contained (it duplicates its CSS rather than sharing a stylesheet).

**Deployment chain:** edit file → commit to `main` on GitHub → Netlify auto-builds and deploys in 1–5 minutes. CDN caching can hide changes for a few extra minutes after deploy completes.

When asked to verify changes are live, **re-fetch the live URL** rather than assuming the source matches the deployment. Netlify deploys can lag GitHub by several commits if a build fails silently or the wrong branch is configured.

> **Known incident (Jun 1, 2026):** after the GitHub repo rename, `main` was correct but livefreejetski.com continued serving an older build (old email + old rental-agreement PDF link) — a sign the repo rename can sever Netlify's webhook. If `main` and the live page disagree, suspect the Netlify↔GitHub connection first and check the Netlify Deploys log before assuming cache lag.

---

## 3. Pages

All 5 are live at the URLs below. Each links back to booking and to the other content pages via the shared nav + footer pattern.

| File | URL | Role |
|------|-----|------|
| `index.html` | `/` | Home — hero, fleet, how-it-works, lakes, pricing, certificates, FAQ, contact |
| `guide.html` | `/guide.html` | "Renting a Jet Ski in NH: The Complete Guide" |
| `tutorial.html` | `/tutorial.html` | "How to Ride a Sea-Doo: A First-Timer's Tutorial" |
| `boat-vs-jet-ski.html` | `/boat-vs-jet-ski.html` | "Renting a Boat vs. a Jet Ski in NH" |
| `boating-license.html` | `/boating-license.html` | "Do You Need a Boating License to Rent a Jet Ski in NH?" |

The 4 content pages share a near-identical structure: **nav → article → "Keep reading" related-links block → footer**. `index.html` is structurally different (single-page layout with anchored sections).

---

## 4. Files in the repo

Listed below are files actually referenced by the HTML. Anything else in the repo is unreferenced (working files / archive material) — see §5.

### HTML (5)
`index.html`, `guide.html`, `tutorial.html`, `boat-vs-jet-ski.html`, `boating-license.html`

### Images referenced (14)
- **Home hero:** `hero-2skis.jpg` (desktop), `hero-2skis-mobile.jpg` (mobile media query)
- **Social/OG image:** `hero-both-seadoos.jpg` (used in `og:image` and JSON-LD on every page)
- **Fleet gallery (home):** `sk1-front.jpg`, `sk1-side.jpg`, `sk1-rear.jpg` (SK-01); `sk2-front.jpg`, `sk2-side.jpg`, `sk2-rider.jpg` (SK-02)
- **Section / hero photos:** `jetski-sunset.jpg` (home contact + guide.html hero), `delivery-wake155.jpg` (home delivery section + boating-license.html hero), `gtr230-beach-anchored.jpg` (home pricing area + boat-vs-jet-ski.html hero); `sk2-rider.jpg` doubles as the tutorial.html hero
- **Map:** `nh-service-map.svg` (lakes-served service-area map on home)

### Documents (3)
- `LiveFreeJetSki-Rental-Agr.pdf` — linked from the pricing "Digital Agreement" row, the requirements checklist, and the footer on home. (Replaced the old `NH-Jet-Fun-Rental-Agreement.pdf`, which is still in the repo but now unreferenced — see §5.)
- `2015_SeaDoo_Wake_.pdf` — Sea-Doo Wake 155 (SK-01) operator's guide. Linked from the "Operator's Guide → View PDF" row in the SK-01 fleet card on index.html (`href="/2015_SeaDoo_Wake_.pdf"`).
- `2018_Sea_doo_GTR_.pdf` — Sea-Doo GTR 230 (SK-02) operator's guide. Linked from the "Operator's Guide → View PDF" row in the SK-02 fleet card on index.html (`href="/2018_Sea_doo_GTR_.pdf"`).

### SEO / crawler (3)
`sitemap.xml`, `robots.txt`, `llms.txt`

### Netlify config (1)
`_redirects` — 301s `nhjetfun.com/*` and `www.nhjetfun.com/*` to `livefreejetski.com/:splat`

### Documentation
`PROJECT_INSTRUCTIONS.md` (this file).

---

## 5. Unreferenced files currently in the repo

These exist in `main` but no HTML page references them. They are not deployed onto any page; Netlify still serves them at their path but they bloat the repo and aren't part of the live experience. Likely cleanup candidates:

- `2Skiis_sm.jpg` — source photo the home hero was cropped from (may want to keep as archive)
- `NH-Jet-Fun-Rental-Agreement.pdf` — the old rental agreement, superseded by `LiveFreeJetSki-Rental-Agr.pdf`. No page links it anymore. (Consider keeping briefly in case any external/printed link still points at it, then remove.)
- `owner-jeep-trailer.jpg` — purpose unknown
- `map-current.png`, `map-updated.png`, `map-v3.png` — looks like iteration versions of the service-area map (the live map is the SVG)
- `preview-desktop.png`, `preview-mobile.png` — preview screenshots, not used by any page

---

## 6. Design system / styling conventions

Every page declares the same CSS custom properties at the top of its `<style>` block — they are the canonical site palette. **Keep all new color work referencing these variables** rather than hard-coding hex values.

```css
:root{
  --navy:#0a1628;   /* darkest blue — content page footer bg, #contact bg */
  --deep:#0d2244;
  --ocean:#1a4a7a;  /* dark blue — good contrast on light backgrounds */
  --sky:#2d7dd2;    /* medium blue — "Jet" word accent, link hovers */
  --wave:#4db6e8;   /* light blue — links on dark backgrounds (content page footers, #contact) */
  --foam:#e8f4fd;   /* near-white blue — hover on dark backgrounds */
  --sand:#f5ede0;   /* warm tan — home page footer bg */
  --gold:#e8a020;
  --coral:#e85f2d;
  --white:#ffffff;
  --off:#f8fafc;
  --text:#1a2535;
  --muted:#5a7090;
}
```

### Footer conventions (different between home and content pages)

- **Content pages** (`guide.html`, `tutorial.html`, `boat-vs-jet-ski.html`, `boating-license.html`): dark navy bg, links auto-styled to `--wave` via the global `footer a{color:var(--wave)}` rule. The footer is a `<footer><div class="footer-inner">…</div></footer>` structure with two columns: brand blurb + a column of `<p><a>` link rows.
- **Home page** (`index.html`): light tan bg, flat one-line layout. Footer links use `--text` (dark) with `--sky` on hover. The footer email is manually inline-styled to `--sky` with `--ocean` on hover (no shared `footer a{}` rule — every link in the home footer carries its own inline styling).

### Nav conventions
- All pages share the same top nav structure with "Book" / "Book Now" CTA linking to `https://bookings.nhjetfun.com`.
- Content pages link back to home anchors (`#fleet`, `#lakes`, `#pricing`, `#faq`); home page has internal anchor nav.

### Key copy conventions
- **Delivery model:** we meet customers at the lake's public launch ramp — **not** at their cabin or dock. Don't reintroduce dock/cabin language.
- **Domain spelling:** LiveFreeJetSki.com (mixed case) in body copy. (Old "NHJetFun.com" copy should be updated wherever it still appears.)
- **Rental window:** Saturday 5:00 PM → following Saturday 10:00 AM. Season May 30 – Oct 15.
- **Pricing:** SK-01 Wake 155 = $1,250/wk; SK-02 GTR 230 = $1,950/wk. 15% non-refundable reservation deposit + $900 refundable security deposit.
- **Service area:** central and southern NH, from MA line north to Squam Lake. Squam is the northernmost lake served. No lakes north of Squam, no saltwater (no Great Bay), no public waters under 75 acres.
- **Location text:** "Hampstead, New Hampshire" in HTML. (The rental agreement PDF currently says "East Hampstead, NH" — minor inconsistency worth a one-time fix in a future PDF revision.)

---

## 7. Things that look like they should be linked but aren't / quirks

- The home page nav still anchors to `#guides` for an "In-Depth Guides" section that lives on the home page. The 4 content pages don't share that anchor — they link directly to `/guide.html`, `/tutorial.html`, etc.
- `index.html` contains JavaScript fallback `alert()` calls for a contact form that no longer exists in the rendered page. The alerts now reference info@livefreejetski.com and are unreachable in normal use — safe to leave or remove during a future cleanup pass.
- The home page social meta image (`og:image`) is `hero-both-seadoos.jpg`, **NOT** the current `hero-2skis.jpg` hero. Updating it requires re-cropping for the 1200×630 social preview ratio.
- Commit messages on `main` are mostly the GitHub web-UI default "Add files via upload" — so `git log` is not a useful change history yet. See §10 for a fix.

---

## 8. When making changes — workflow Claude should follow

1. **Verify before editing.** Don't trust this doc or prior chat memory on the current state of any specific string, file, or page. Re-clone or re-fetch when accuracy matters. The user has a standing preference: when claiming something is on the live site, verify it on the actual rendered page before stating it.
2. **Edit at the source** — `index.html` etc. on GitHub `main`. Don't try to edit Booqable from here (it's a separate hosted product) and don't propose changes to Netlify config without checking the dashboard first.
3. **Output a complete updated file** the user can drop into GitHub via "Add file → Upload files" (their default workflow). Provide a clear diff summary alongside it. **Do not paste the full file content inline in chat** — the user prefers the file attachment alone and finds inline pastes redundant. The exception is short snippets (a few lines) that illustrate what changed; full-file dumps stay out of chat.
4. **Use CSS variables from §6** for any color change. Don't hard-code hexes. Don't introduce new color tokens without flagging it.
5. **Preserve the legal entity reference** (Veralase LLC) in footers, About, and structured data unless explicitly told to remove it.
6. **For deployment verification**, re-fetch https://livefreejetski.com/ (and the specific page) after the user has committed. Confirm both that the change rendered and that the deploy actually fired (don't assume cache lag if `main` and live disagree — see the §2 incident note). Report any lag or sync gap honestly.

---

## 9. Common gotchas

- Site uses **5 pages, not 1**. Older notes called it a "single-page site" — that's stale.
- Photos are separate files referenced by root-relative paths like `src="/sk1-side.jpg"` and `background-image:url("/hero-2skis.jpg")`. Not embedded.
- **No build step.** Don't suggest webpack, Vite, Tailwind compilation, etc. — every page declares its own inline CSS.
- `index.html` footer ≠ content-page footer. Different background, different markup, different link styling. A "fix all footers" instruction usually means just `index.html`.
- **Booqable plan limit:** the current plan is Standard. Booqable's embedded booking widget requires the Grow plan, which is why the site links out to bookings.nhjetfun.com rather than embedding.

---

## 10. Recommended cleanup / process improvements

These are suggestions for the user — not changes Claude has already made.

### File / repo hygiene
- Delete the unreferenced files in §5 (or move the source-photo `2Skiis_sm.jpg` to a `_archive/` folder if you want to keep originals). This now includes the superseded `NH-Jet-Fun-Rental-Agreement.pdf`.

### Commit messages
- Switch from the default "Add files via upload" to short descriptive messages — e.g., "Fix footer email color and BOOK button wording". The GitHub web UI lets you type a message before clicking Commit. Doing this gives Claude (and future-you) a usable change history, removing the need to maintain a separate "Recent Changes" log in this file.

### A `_archive/` folder
- For prior versions of pages (like the deleted `index.backup.20260524.html`) and source photos, a `/_archive/` subfolder is cleaner than leaving them at the repo root where they look active.

---

## 11. Quick links

| | |
|---|---|
| Live site | https://livefreejetski.com |
| Booking | https://bookings.nhjetfun.com |
| GitHub | https://github.com/beandm15/livefreejetski.com |
| Netlify | https://app.netlify.com (site name may still be `nhjetfun` — verify) |
| Domain registrar | Namecheap |
| Booking platform | Booqable (Standard plan) |
| Business contact | info@livefreejetski.com |
