# JetSki_References.md — Reference Sources & Background

**Project:** Jet Ski Rentals (Live Free Jet Ski)
**Purpose:** Quick links, fleet details, key documents, vendor/account references, and a working glossary for Live Free Jet Ski. Use these to find the right source fast; verify any figure against the live site or the current file before relying on it.
**Last updated:** 2026-07-26

---

## 1. Business at a Glance

- **Business:** Live Free Jet Ski (formerly NH Jet Fun) — weekly Sea-Doo jet ski rentals, Hampstead, NH.
- **Legal entity:** Veralase LLC d/b/a Live Free Jet Ski.
- **Owner:** David Bean (GitHub: beandm15).
- **Model:** weekly rentals (Sat 5:00 PM → following Sat 10:00 AM), season May 30 – Oct 15; customers met at the lake's public launch ramp.
- **Service area:** central & southern NH, MA line north to Squam Lake (northernmost served); no lakes north of Squam, no saltwater, no public waters under 75 acres.

## 2. Quick Links

| | |
|---|---|
| Live site | https://livefreejetski.com |
| Booking | https://bookings.nhjetfun.com (Booqable, Standard plan — separate from the codebase, still on old domain) |
| GitHub repo | https://github.com/beandm15/livefreejetski.com (public, `main` branch) |
| Netlify | https://app.netlify.com (site name may still be `nhjetfun` — verify) |
| Domain registrar | Namecheap (nameservers pointed at Netlify) |
| Business email | info@livefreejetski.com |

> Per the owner's standing preference: when stating that specific content is on the live site, re-fetch the actual rendered page and confirm it's there before saying so.

## 3. The Fleet

| Unit | Craft | Year | Weekly price | Operator guide (in repo/Docs) |
|---|---|---|---|---|
| **SK-01** | Sea-Doo Wake 155 | 2015 | $1,250/wk | `2015_SeaDoo_Wake_.pdf` |
| **SK-02** | Sea-Doo GTR 230 | 2018 | $1,950/wk | `2018_Sea_doo_GTR_.pdf` |

Deposits (both units): **15% non-refundable reservation deposit + $900 refundable security deposit.** Verify current pricing on the live site before quoting.

## 4. Key Documents & Where They Live

Folders below are under the **Jet Ski Rentals** folder root. Each working subfolder holds one kind of finished/in-progress work; the inventories below reflect the folders as of **2026-07-26** (verify against the current folder before relying on any single filename). Put superseded material in each folder's **Archive/** rather than leaving stale duplicates.

### 4a. Docs/ — legal documents & fleet guides (editing → finalization)

Working area for legal and customer-facing forms: the rental agreement is drafted/edited here (`.docx`) and finalized to `.pdf` for the website and for customer signing. Also holds the Sea-Doo operator guides.

- `LiveFreeJetSki-Rental-Agr.pdf` — **current, finalized rental agreement** (linked from the site's pricing "Digital Agreement" row, the requirements checklist, and the footer). This is the version customers sign.
- `LiveFreeJetSki-Rental-Agr_rev4.docx` — **editable source** of the current rental agreement; edit here, then re-export the PDF above. Keep defined terms and the Veralase LLC d/b/a Live Free Jet Ski party name consistent.
- `2015_SeaDoo_Wake_.pdf` — Sea-Doo Wake 155 operator's guide (SK-01); linked from the SK-01 fleet card on the site.
- `2018_Sea_doo_GTR_.pdf` — Sea-Doo GTR 230 operator's guide (SK-02); linked from the SK-02 fleet card.
- **Docs/Archive/** — superseded / secondary documents:
  - `LiveFreeJetSki-Rental-Agr_rev3.docx` — prior revision of the rental agreement.
  - `LFJS_ANS_Agreement.docx` — Aquatic Nuisance Species (ANS) / clean-drain-dry acknowledgment draft.
  - `Short_Sizes.png` — sizing reference image (apparel/shorts).

> Rental-agreement edits touching liability, waiver, or insurance language should be reviewed by qualified counsel or the insurance broker before use (see Instructions §7). Mark any spot needing an owner decision or a missing fact with a visible `[CONFIRM —]` placeholder.

### 4b. Expenses/ — company expense repository (receipts)

Flat repository of business-expense receipts, one PDF per purchase (~29 receipts as of 2026-07-26; no subfolders). **Naming convention:** date-prefixed `M-DD` or `MM-DD`, then vendor and/or item, e.g. `06-30_Overton_life_jackets.pdf`, `6-16 Boat parts - ski ladder.pdf`. Dates run late May through late July of the current season. Recurring **vendors:** Amazon, Overton's, GotPrint, eBay, Facebook Marketplace, Luma AI. Rough spend **categories:**

- **Life jackets / PFDs** — multiple Amazon and Overton's receipts (e.g. `5-23_Amazon_LifeJackets.pdf`, `5-27_Overtons_jackets.pdf`, `06-30_Overton_life_jackets.pdf`, `7-13 life jackets.pdf`, `7-26 life jackets.pdf`).
- **Boat / jet-ski parts** — tow straps, pressure gauge, fuel pump, ski ladder, cable strap, Wake seat, misc. (`6-14 … tow straps.pdf`, `6-15 … pressure guage.pdf`, `6-20 … fuel pump.pdf`, `6-16 … ski ladder.pdf`, `7-23 Wake Seat eBay.pdf`, several `Boat parts` files).
- **Print collateral** — brochures/rack cards and road signs from GotPrint (`5-25_brochures_Gotprint.pdf`, `6_11_Gotprint_brochures2_…pdf`, `5-25_roadsigns_Gotprint.pdf`, `7-22 signs.pdf`).
- **Brochure holders & stickers** — Amazon (`5-27_Amazon_brochureholder.pdf`, `6-3_Amazon_brochureholder.pdf`, `6-1_Amazon_sticker.pdf`).
- **Apparel** — branded shorts (`6-1_Amazon_shorts.pdf`, `6-1_Amazon_shorts_more.pdf`).
- **Dock/handling & trailer** — dock bumpers (`5-27_bumpers_ eBay.pdf`), double trailer (`6_22_Dbl_Trailer_Facebook.pdf`).
- **Software / media** — Luma AI (`6-15_Luma_AI_Receipt-…pdf`).

> Treat receipts as private business records. Useful as the source for season expense totals by category/vendor when needed.

### 4c. Brochure/ — brochure & rack-card development (print-ready)

Print production files for the rack card / brochure and its placement. Current brand is **Live Free Jet Ski**; old **NH Jet Fun** artwork is in Archive.

- `LiveFreeJetSki-RackCard-4x9-PRINT-CMYK.pdf` — combined front+back rack card, 4×9, CMYK, print-ready.
- `LiveFreeJetSki-RackCard-FRONT-4x9-PRINT-CMYK.pdf` / `-BACK-4x9-PRINT-CMYK.pdf` — individual front and back print files.
- `Brochure_holder_stickers.pdf` — stickers for the brochure holders.
- `Labels_OL1930-07.docx` — OnlineLabels template OL1930 (label sheet layout).
- `LiveFreeJetSki-Brochure-Placement-Route.xlsx` — the physical placement/distribution route for brochures (where holders are stocked).
- **Brochure/Archive/** — superseded `NH-Jet-Fun-RackCard-*` print files (front/back/combined) and `preview-front.png` / `preview-back.png` proofs.

### 4d. Sign/ — lawn / road sign development (print-ready)

Sign artwork for lawn and roadside placement. (Folder stores as lowercase `sign/` in Dropbox.) Current **Live Free Jet Ski** artwork plus retired **NH Jet Fun** versions.

- `LiveFreeJetSki_LawnSign_24x18_blue.pdf` — current 24×18 lawn sign (blue).
- `LiveFreeJetSki_LawnSign_35.875x23.875_blue.pdf` — larger landscape lawn sign (blue).
- `LiveFreeJetSki_TallSign_23.875x35.875_blue.pdf` — portrait/tall sign (blue).
- **Retired (NH Jet Fun brand):** `NHJetFun_LawnSign_24x18_blue.pdf`, `NHJetFun_LawnSign_24x18_0.pdf`, `NHJetFun_LawnSign_24x18_1.pdf`, `24x18_ski_sign.jpg` — old-brand versions and a source JPG; candidates to move to an Archive subfolder.

### 4e. Rental Agr/ — finished / signed rental agreements (customer PII — keep private)

Completed, customer-signed rental agreements, one PDF per booking (5 signed agreements on file as of 2026-07-26; an empty `Archive/` subfolder exists). **These contain customer personal information — do not reproduce names, addresses, IDs, or payment details in chat, examples, memory, or external references** (Instructions §7). Filenames follow a `LFJS_[customer]_Agr_signed.pdf` pattern, though naming is inconsistent across files (some use `LFJS [Name].pdf`, `LiveFreeJetSki_Agr_[Name].pdf`, or `LFJS_[Name]_agr.pdf`) — worth standardizing going forward.

### 4f. Other folders (unchanged)

- **Insurance/** — rental-boat supplemental policy (One80) and application material.
- **LiveFreeJetSki_Website/** — the site source; start from its `PROJECT_INSTRUCTIONS.md` and `CLAUDE.md` for any site work. This knowledge-base triplet (Instructions / Guidelines / References) also lives here.
- **Archive/** (root) — retired site versions (`livefreejetski.com`, old `nhjetfun.com` material) and superseded files.

## 5. Website Structure & File Inventory (Reference)

**Tech & deployment:** pure static site — **no build step, no framework, no package manager.** Each page is hand-edited, self-contained HTML with inline `<style>`/`<script>` (CSS is duplicated per page, not shared). Deploy chain: edit file → commit to `main` on GitHub → Netlify auto-builds and deploys in 1–5 minutes. Hosting is Netlify (auto-deploy from `main`); DNS is Namecheap with nameservers pointed at Netlify.

**Five live pages**, each links back to booking and to the other content pages via a shared nav + footer pattern:

| File | URL | Role |
|---|---|---|
| `index.html` | `/` | Home — hero, fleet, how-it-works, lakes, pricing, certificates, FAQ, contact |
| `guide.html` | `/guide.html` | "Renting a Jet Ski in NH: The Complete Guide" |
| `tutorial.html` | `/tutorial.html` | "How to Ride a Sea-Doo: A First-Timer's Tutorial" |
| `boat-vs-jet-ski.html` | `/boat-vs-jet-ski.html` | "Renting a Boat vs. a Jet Ski in NH" |
| `boating-license.html` | `/boating-license.html` | "Do You Need a Boating License to Rent a Jet Ski in NH?" |

### 5a. Referenced files (actually used by the HTML)

**Images (14):**
- **Home hero:** `hero-2skis.jpg` (desktop), `hero-2skis-mobile.jpg` (mobile media query).
- **Social/OG image:** `hero-both-seadoos.jpg` (used in `og:image` and JSON-LD on every page).
- **Fleet gallery (home):** `sk1-front.jpg`, `sk1-side.jpg`, `sk1-rear.jpg` (SK-01); `sk2-front.jpg`, `sk2-side.jpg`, `sk2-rider.jpg` (SK-02).
- **Section / hero photos:** `jetski-sunset.jpg` (home contact + `guide.html` hero); `delivery-wake155.jpg` (home delivery section + `boating-license.html` hero); `gtr230-beach-anchored.jpg` (home pricing area + `boat-vs-jet-ski.html` hero); `sk2-rider.jpg` doubles as the `tutorial.html` hero.
- **Map:** `nh-service-map.svg` (lakes-served service-area map on home; the live map is the SVG).

**Documents (3):**
- `LiveFreeJetSki-Rental-Agr.pdf` — linked from the pricing "Digital Agreement" row, the requirements checklist, and the footer on home. (Replaced the old `NH-Jet-Fun-Rental-Agreement.pdf`.)
- `2015_SeaDoo_Wake_.pdf` — SK-01 Wake 155 operator's guide (linked from the SK-01 fleet card).
- `2018_Sea_doo_GTR_.pdf` — SK-02 GTR 230 operator's guide (linked from the SK-02 fleet card).

**SEO / crawler (3):** `sitemap.xml`, `robots.txt`, `llms.txt`.

**Netlify config (1):** `_redirects` — 301s `nhjetfun.com/*` and `www.nhjetfun.com/*` to `livefreejetski.com/:splat`.

### 5b. Unreferenced files in the repo (cleanup candidates)

These exist in `main` but no HTML page references them — not part of the live experience; Netlify still serves them at their path but they bloat the repo:
- `2Skiis_sm.jpg` — source photo the home hero was cropped from (may keep as archive).
- `NH-Jet-Fun-Rental-Agreement.pdf` — the old rental agreement, superseded by `LiveFreeJetSki-Rental-Agr.pdf`; no page links it. (Consider keeping briefly in case an external/printed link still points at it, then remove.)
- `owner-jeep-trailer.jpg` — purpose unknown.
- `map-current.png`, `map-updated.png`, `map-v3.png` — iteration versions of the service-area map (the live map is the SVG).
- `preview-desktop.png`, `preview-mobile.png` — preview screenshots, not used by any page.

## 6. Vendors & Accounts

- **Hosting:** Netlify (auto-deploy from GitHub `main`).
- **Domain:** Namecheap.
- **Booking:** Booqable (Standard plan) at `bookings.nhjetfun.com`.
- **Source control:** GitHub (`beandm15/livefreejetski.com`).
- **Insurance:** rental-boat supplemental via One80 (see Insurance folder).
- **Print:** GotPrint (rack cards, road signs).
- **Retail suppliers:** Amazon, Overton's, eBay, Facebook Marketplace (life jackets, boat parts, apparel, trailer, dock bumpers — see Expenses).

## 7. External Reference Categories

Use these when a question needs current authority; verify a source actually contains a fact before citing it.

- **NH boating law & registration:** NH Fish and Game / NH Marine Patrol for boater education (NH boat/PWC operation rules), registration, and safe-boating certificate requirements — relevant to the `boating-license.html` and `guide.html` content.
- **Coast Guard / safety:** USCG requirements for PFDs (life jackets) and safe operation.
- **Manufacturer:** Sea-Doo (BRP) operator guides and specs for the Wake 155 and GTR 230.
- **Platform docs:** Netlify (deploys/redirects), Booqable (plans/booking widget), Namecheap (DNS), GitHub (repo/Pages).

> Site content that states legal or licensing requirements (boating license, minimum age, safety rules) should be checked against current NH Fish & Game / Marine Patrol guidance before publishing changes — regulations change, and the site's claims should be accurate.

## 8. Glossary

- **SK-01 / SK-02** — the two rental units (Sea-Doo Wake 155 and Sea-Doo GTR 230).
- **Rental window** — the weekly period a unit is booked: Saturday 5:00 PM to the following Saturday 10:00 AM.
- **Reservation deposit** — 15% non-refundable deposit to hold a booking.
- **Security deposit** — $900 refundable hold against damage.
- **Booqable** — the third-party booking platform (on `bookings.nhjetfun.com`), separate from the marketing site.
- **`_redirects`** — the Netlify file that 301-redirects old `nhjetfun.com` URLs to `livefreejetski.com`.
- **Veralase LLC** — the legal entity operating as Live Free Jet Ski.
- **PFD** — Personal Flotation Device (life jacket).
- **ANS** — Aquatic Nuisance Species; NH clean-drain-dry rules for watercraft (see `Docs/Archive/LFJS_ANS_Agreement.docx`).
- **`.fuse_hidden*`** — stale Dropbox/FUSE mount artifacts, not project files; safe to remove.

---
*This is reference material, not legal or insurance advice. Verify current pricing, dates, and legal/licensing statements against the live site and primary sources, and have qualified counsel or the insurance broker review changes to liability, waiver, or insurance language before use.*
