# SESSION RECAP 2 — Cap10 Website Redesign Prototype
_Repo: tracy330/cap10-website-redesign — Updated 30 April 2026_

This document captures the work completed across the redesign prototype sessions, layered on top of the original SESSION-RECAP. It is the single reference for what is in main, what is in the v1/v2/v3 variants, and what remains to do.

---

## 1. Three missing items (added in earlier session)
- Fifth sector ("mission-critical business services") added to the Our Firm sector list.
- Regulatory Disclosure block added to Responsible Investing with MIFIDPRU 8 and Responsible Investment Policy links.
- Heading style fix applied so editorial typography matches across pages.

## 2. Full content audit (read-only) — all 7 pages
A page-by-page audit was conducted comparing the prototype against cap10partners.com. Each finding was reviewed with the user and decisions were captured before any code changes were made.

## 3. Audit fixes — 10 atomic commits
Fixes applied one per commit, each verified live with cache-bust before moving on.

| # | Commit | Page | Change |
|---|---|---|---|
| 1 | a2bbd3e | Our Firm | Removed "Thirteen investors and operators" line. |
| 2 | b0b5e7f | Team | Reordered Partners group so Mandar appears before Calum. |
| 3 | 95b5139 | Portfolio | Reverted "How we invest" copy to the original wording. |
| 4 | e4f26d4 | Responsible Investing | Softened the Compass × Sureserve copy to reflect that conversations are still in progress. |
| 5 | 4dc45d4 | Responsible Investing | Restored paragraph break in the intro; second paragraph styled in matching Fraunces type. |
| 6 | 35560be | Responsible Investing | Added "Interested in partnering with us? Contact us" CTA at bottom. |
| 7 | 77542ae | Contact | Added styled mailto: form, ir@cap10partners.com IR address, bottom CTA. |
| 8 | 92955a1 | Insights | Added media enquiries line (corporate@cap10partners.com), bottom CTA; verified Sureserve × Duality date 11 April 2024. |
| 9 | 751d1e1 | Top nav | Added Investors login link to nav (target=_blank, eFront URL). |
| 10 | 16e1ba1 | Footer | Terms → "Terms & Conditions"; added Investors login on every page footer. |

## 4. Video variants — initial build
Three variants were created from the 16e1ba1 baseline, each with a single Mixkit hero clip swapped for the original CMS hero video.

- **v1** (commit d1d2d8a) — wind turbine landscape (Mixkit 34102)
- **v2** (commit ce52b2e) — solar panel installers (Mixkit 23491)
- **v3** (commit 69896b2) — coastal aerial (Mixkit 1955)

Variant v3 required several attempts to debug a 9-byte upload bug (window state wiped on navigation). Final fix: trigger the Blob download inline within the fetch().then() callback so JS state is alive at the moment of file creation.

## 5. Sculpture image fix on Our Firm — commit 9e03a78
The Our Firm hero strap previously cropped the image with object-fit: cover and object-position: center 30%, hiding the sculpture and showing only the artist's face. Updated to object-fit: contain with the dark #1a1a1a parent acting as a gallery-style frame. Both the sculptor and her artwork are now fully visible in context.

## 6. v1 rebuilt with three-video alternating layout — commits a10344b → 2a2690a
The user requested that v1 carry **three videos inline with the wording**, mirroring the Three Promises section on the main prototype, with each video meaning-matched to its block.

**Pairings (locked):**
- 01 Our focus → solar panel installers (Mixkit 23491) — essential infrastructure
- 02 How we work → wind turbine landscape (Mixkit 34102) — engineered, deliberate process
- 03 Why ESG matters → coastal aerial (Mixkit 1955) — stewardship, long-term

**a10344b** introduced a new "promises-rail" structure with three alternating side-by-side rows (text/video, video/text, text/video) using CSS grid. All three videos autoplay, muted, loop, playsinline. Mobile collapses to single column with the video stacked above each block. Same wording as the main prototype, no copy changes.

**2a2690a** moved the Three Promises rail to sit directly after the hero section so the videos and wording appear immediately when scrolling past the wind turbine hero. Previously buried below the founder block at y≈2200, now at y≈1442.

## 7. State of the four files
- **index.html** — main prototype with all 10 audit fixes and the sculpture object-fit fix.
- **index-v1.html** — wind hero + three-video alternating Three Promises rail (solar/wind/coastal); rail positioned directly under hero.
- **index-v2.html** — solar hero only (single Mixkit clip); Three Promises section unchanged from main. To be revisited next week with three solar/grid clips.
- **index-v3.html** — coastal hero only (single Mixkit clip); Three Promises section unchanged from main. To be revisited next week with three nature/landscape clips.

## 8. Outstanding items for next week
- Find three new Mixkit clips per theme for v2 (solar / energy infrastructure) and v3 (stewardship / scale / nature). User to preview each candidate URL in browser since the agent cannot browse Mixkit's catalogue.
- Apply the same three-video alternating Three Promises layout to v2 and v3 once clips are confirmed.
- Optional: review v1 pairings on second viewing to see if any of the three matches need swapping.

## 9. Working patterns established
- Atomic commits: one fix per commit, verified live with cache-bust before moving on.
- Integrity gate before every download: brace balance (must match), 5/5 script tags, every script block parses via new Function(code).
- Downloads must be triggered from github.com origin (not raw.githubusercontent.com) and inline within the fetch callback.
- Commits verified via the GitHub API plus a SHA-pinned raw fetch before declaring done.
