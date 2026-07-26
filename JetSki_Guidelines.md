# JetSki_Guidelines.md — Best Practices & Guidelines

**Project:** Jet Ski Rentals (Live Free Jet Ski)
**Purpose:** Soft guidance, business facts, and conventions (not hard instructions) for maintaining the website, documents, and operations of Live Free Jet Ski. These are the working defaults; the live site and current source files govern where they disagree.
**Last updated:** 2026-07-26

---

## 1. What's at Stake — The Governing Principle

Live Free Jet Ski is a small, seasonal, owner-run rental business. Its value lives in a clean brand, an accurate website, sound rental/liability paperwork, and controlled costs. So the guiding test for almost every change is: **does this keep the brand consistent, the public information accurate, and the customer experience simple — without breaking the site or creating liability exposure?**

Posture: lean, founder-led, cost-conscious. Move quickly on small edits, but verify before claiming something is live, and don't push to GitHub or change legal/insurance language without the owner's sign-off.

## 2. Business Facts & Copy Conventions

Keep these consistent across the site, documents, and collateral. **Verify against the live site before relying on any figure** — pricing and dates change season to season.

| Item | Current value | Notes |
|---|---|---|
| **Business name** | Live Free Jet Ski | Formerly **NH Jet Fun** — update stale branding wherever it still appears. |
| **Legal entity** | Veralase LLC d/b/a Live Free Jet Ski | Keep in footers, About, JSON-LD, rental agreement. **Do not strip.** |
| **Location** | Hampstead, New Hampshire | Rental-agreement PDF currently says "East Hampstead, NH" — minor inconsistency to fix in a future PDF revision. |
| **Owner** | David Bean (GitHub: beandm15) | |
| **Business email** | info@livefreejetski.com | Was bookings@nhjetfun.com. |
| **Fleet** | SK-01 Sea-Doo Wake 155 (2015); SK-02 Sea-Doo GTR 230 (2018) | See JetSki_References for operator guides. |
| **Pricing** | SK-01 Wake 155 = $1,250/wk; SK-02 GTR 230 = $1,950/wk | 15% non-refundable reservation deposit + $900 refundable security deposit. |
| **Rental window** | Saturday 5:00 PM → following Saturday 10:00 AM | Weekly rental model. |
| **Season** | May 30 – Oct 15 | |
| **Delivery model** | Meet customers at the lake's public launch ramp | **Not** at their cabin or dock — don't reintroduce dock/cabin language. |
| **Service area** | Central & southern NH, from the MA line north to Squam Lake | Squam is the northernmost lake served. No lakes north of Squam, no saltwater (no Great Bay), no public waters under 75 acres. |
| **Domain spelling** | LiveFreeJetSki.com (mixed case) in body copy | Update old "NHJetFun.com" copy wherever it appears. |

## 3. Website Editing Workflow

The site is a **5-page static site** (`index.html`, `guide.html`, `tutorial.html`, `boat-vs-jet-ski.html`, `boating-license.html`) — **no build step, no framework, no package manager.** Each page is hand-edited, self-contained HTML with inline `<style>`/`<script>`. Follow this workflow:

1. **Verify before editing.** Don't trust this doc or prior chat on the current state of any string, file, or page. Read the source file, and re-fetch the live page when accuracy matters.
2. **Edit at the source** — the HTML files in `LiveFreeJetSki_Website`. Don't try to edit Booqable (the separate hosted booking product) and don't change Netlify config without checking the dashboard first.
3. **Output a complete updated file** the owner can drop into GitHub via "Add file → Upload files" (their default workflow), plus a clear diff summary. **Do not paste full file content inline in chat** — the owner finds that redundant. Short snippets illustrating what changed are fine.
4. **Push to GitHub only with permission.** Deploy chain: commit to `main` → Netlify auto-builds and deploys in 1–5 minutes. Never push without the owner's explicit approval. **Exception — the knowledge-base triplet:** `JetSki_Instructions.md`, `JetSki_Guidelines.md`, and `JetSki_References.md` have standing owner authorization to be updated in both Dropbox and GitHub without asking, and must be kept in sync across both (see JetSki_Instructions §10). This exception covers only those three files.
5. **Verify the deploy.** After the owner commits, re-fetch https://livefreejetski.com/ (and the specific page). Confirm both that the change rendered and that the deploy actually fired. CDN caching can hide changes for a few extra minutes after a deploy completes. If `main` and the live page disagree, suspect the Netlify↔GitHub webhook first (it can break on a repo rename) and check the Netlify Deploys log before assuming cache lag.

> **Known incident (Jun 1, 2026):** after the GitHub repo was renamed (nhjetfun.com → livefreejetski.com), `main` was correct but the live site kept serving an older build (old email + old rental-agreement PDF link) — a sign the repo rename can sever Netlify's webhook. Netlify deploys can lag GitHub by several commits if a build fails silently or the wrong branch is configured. The Netlify site name may also still be `nhjetfun` (a GitHub rename doesn't rename the Netlify site) — verify in the dashboard.

## 4. Design System / Styling Conventions

Every page declares the same CSS custom properties at the top of its `<style>` block — the canonical site palette. **Use these variables for any color work; don't hard-code hex values, and flag before introducing a new color token.**

```css
:root{
  --navy:#0a1628;   /* darkest blue — content page footer bg, #contact bg */
  --deep:#0d2244;
  --ocean:#1a4a7a;  /* dark blue — good contrast on light backgrounds */
  --sky:#2d7dd2;    /* medium blue — "Jet" word accent, link hovers */
  --wave:#4db6e8;   /* light blue — links on dark backgrounds */
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

Layout conventions to respect:

- **Page structure.** The 4 content pages share a near-identical structure: **nav → article → "Keep reading" related-links block → footer**. `index.html` is structurally different — a single-page layout with anchored sections (`#fleet`, `#lakes`, `#pricing`, `#faq`, `#contact`, `#guides`).
- **Footers differ between home and content pages.**
  - *Content pages* (`guide`, `tutorial`, `boat-vs-jet-ski`, `boating-license`): dark navy background; links auto-styled to `--wave` via the global `footer a{color:var(--wave)}` rule. Markup is `<footer><div class="footer-inner">…</div></footer>` with two columns — a brand blurb plus a column of `<p><a>` link rows.
  - *Home page* (`index.html`): light tan background, flat one-line layout. Footer links use `--text` (dark) with `--sky` on hover; the footer email is manually inline-styled to `--sky` with `--ocean` on hover (no shared `footer a{}` rule — every home-footer link carries its own inline styling).
  - A "fix all footers" request usually means **just `index.html`**, since the content pages already share one rule.
- **Nav:** all pages share the top nav with a "Book" / "Book Now" CTA linking to `https://bookings.nhjetfun.com`. Content pages link back to home anchors (`#fleet`, `#lakes`, `#pricing`, `#faq`); the home page uses internal anchor nav (its nav still anchors to a `#guides` "In-Depth Guides" section that lives on the home page — the content pages don't share that anchor and instead link directly to `/guide.html`, `/tutorial.html`, etc.).
- **Images** are separate files referenced by root-relative paths (e.g. `src="/sk1-side.jpg"`, `background-image:url("/hero-2skis.jpg")`), not embedded.

## 5. Legal / Rental Document Guidelines

- Reference the current version in the **Docs** folder before editing; the live rental agreement is `LiveFreeJetSki-Rental-Agr.pdf` (source `.docx` is `LiveFreeJetSki-Rental-Agr_rev4.docx`).
- Keep the legal entity (Veralase LLC d/b/a Live Free Jet Ski) and defined terms consistent throughout.
- Mark any spot needing an owner decision or missing fact with a visible placeholder like `[CONFIRM —]`.
- **Flag anything touching liability, waiver, indemnity, or insurance for counsel/broker review** before use — these are not areas to change on assumption.
- When the site links to the rental agreement, confirm it points at the current PDF, not a superseded one (the old `NH-Jet-Fun-Rental-Agreement.pdf` is retired).

## 6. Common Gotchas & Quirks

- Site is **5 pages, not 1** — older notes calling it "single-page" are stale.
- **No build step** — don't suggest webpack, Vite, Tailwind compilation, etc. Every page declares its own inline CSS.
- **Booqable plan limit:** the current plan is Standard; the embedded booking widget needs the Grow plan, which is why the site links out to `bookings.nhjetfun.com` rather than embedding.
- The booking subdomain is **still on the old domain** (`bookings.nhjetfun.com`) — not yet migrated. Don't "fix" it to the new domain without confirming the migration happened.
- Old nhjetfun.com URLs 301-redirect to livefreejetski.com via the repo's `_redirects` file — preserve those redirects.
- Commit history on `main` is mostly the GitHub default "Add files via upload" — `git log` isn't yet a useful change record. Encourage short descriptive commit messages.
- **Social/OG image:** the home page `og:image` is `hero-both-seadoos.jpg`, **not** the current `hero-2skis.jpg` hero. Updating it requires re-cropping to the 1200×630 social-preview ratio.
- **Orphaned JS:** `index.html` contains JavaScript fallback `alert()` calls for a contact form that no longer exists in the rendered page. They now reference info@livefreejetski.com and are unreachable in normal use — safe to leave or remove during a future cleanup pass.
- **Location inconsistency:** the HTML says "Hampstead, New Hampshire" while the rental-agreement PDF currently says "East Hampstead, NH" — a minor mismatch worth a one-time fix in a future PDF revision.

## 7. Repo Hygiene & Process Recommendations

These are suggestions for the owner, not changes to make unprompted:

- **File/repo cleanup:** several files sit in `main` but aren't referenced by any page (see JetSki_References §5b for the list). They aren't part of the live experience and bloat the repo — candidates to delete or move into an `_archive/` subfolder (keeping source photos like `2Skiis_sm.jpg` as archive if wanted).
- **Commit messages:** switch from the default "Add files via upload" to short descriptive messages (e.g., "Fix footer email color and BOOK button wording"). The GitHub web UI lets you type a message before clicking Commit. This gives a usable change history and removes any need for a separate "recent changes" log.
- **An `_archive/` folder:** for prior page versions and source photos, a `/_archive/` subfolder is cleaner than leaving them at the repo root where they look active.
- **Knowledge-base triplet lives in two places:** the three `.md` files are kept in both Dropbox and the GitHub repo root and must stay in sync (standing authorization to update both — see JetSki_Instructions §10).

## 8. Communication Style

- Lead with the bottom line / change summary; keep it concise and decision-ready.
- For website edits, deliver the updated file plus a short diff; keep full-file dumps out of chat.
- Prefer clean prose and short lists; use tables for fact/term comparisons where they aid clarity.
- Note where the owner's approval is needed (pushing to GitHub) or where counsel/broker should confirm (liability/insurance), and err toward flagging.
