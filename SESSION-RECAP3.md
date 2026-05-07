# SESSION RECAP 3 — Cap10 Website Redesign Prototype

Repo: tracy330/cap10-website-redesign — Updated 7 May 2026

This recap layers on top of SESSION-RECAP and SESSION-RECAP2. It captures the team-page work, the new asset-folder convention, the removal of the Investors login, and the decision to move the build to Webflow.

## 1. Team page — Investment Team reorder and retitle

The Investment Team section was reordered and retitled across all four files (index.html, index-v1.html, index-v2.html, index-v3.html) in a single round of atomic edits.

Order changed from Roel / Christophe / Tigran / Joe / Max to:
- Roel van Ark — Managing Director (was Principal)
- Tigran Petrosyan — Director (was Managing Director)
- Christophe Auber — Vice President (unchanged)
- Joe Baxter — Vice President (was Director)
- Maximilian Dialdas — Associate (unchanged)

Each file received an identical +200 byte delta and passed the integrity gate (brace balance 0, 5/5 script tags, all script blocks parse).

## 2. New convention: assets/ folder for images and PDFs

Going forward, all locally-hosted images and PDFs live under /assets/ at the repo root. Existing partner photos remain on cms.cap10partners.com for now and will be migrated as Tracy extracts them from Strapi.

First asset added:
- assets/neeshal.jpg (81 KB) — Neeshal Rao headshot, replacing the initials placeholder in the Operations & Support section.

Filename and path conventions:
- Lowercase filenames (GitHub Pages is case-sensitive).
- .jpg extension preferred (matches existing CMS convention).
- Path referenced as relative: src="assets/neeshal.jpg".

A duplicate assets/neeshal.jpeg was created during the upload/rename and subsequently deleted to keep the folder clean.

## 3. Investors login removed across all four files

The eFront investor login was retired. Three references were removed from each of index.html, index-v1.html, index-v2.html, index-v3.html:
1. Top nav anchor (.nav-investor).
2. Contact page contact-office-block (eyebrow + portal link).
3. Footer link sitting after Terms & Conditions.

Identical −585 byte delta on each file. Integrity gate passed on all four. Live verification confirmed zero remaining occurrences of "Investors login", "efrontcloud", or "cap10_investors".

The Contact page contact-office strip now shows two blocks (Office + Email) instead of three.

## 4. State of the four files (after this session)

- index.html — main prototype, all team/asset/login changes applied.
- index-v1.html — wind hero + three-video Three Promises rail; team/asset/login changes applied.
- index-v2.html — solar hero (single Mixkit clip); team/asset/login changes applied.
- index-v3.html — coastal hero (single Mixkit clip); team/asset/login changes applied.

## 5. Outstanding from SESSION-RECAP2 (still open)

- Find three new Mixkit clips per theme for v2 (solar / energy infrastructure) and v3 (stewardship / scale / nature). Tracy to preview candidates in browser since the agent cannot browse Mixkit's catalogue.
- Apply the three-video alternating Three Promises layout to v2 and v3 once clips are confirmed.
- Optional: review v1 pairings on second viewing.

## 6. Decision: move to Webflow for production build

The prototype has reached a level of polish where the next step is to rebuild it in Webflow as the production site. Reasons:
- Partner-editable CMS for Team Members, Portfolio Companies, Insights, Sectors, and Documents.
- Proper hosting + custom domain (cap10partners.com or staging subdomain).
- Form submissions on the Contact page handled natively.
- Clean migration path for assets as they are extracted from Strapi.

Investigation agenda for next session:
1. Webflow pricing — Site plans (Basic / CMS / Business) and Workspace seats.
2. Whether CMS plan is sufficient or Business is required (forms, bandwidth, page-level password protection).
3. CMS Collections schema implied by the prototype: Team Members, Portfolio Companies, Insights/News Posts, Sectors, Documents (PDFs).
4. Migration approach — rebuild in Webflow Designer using the prototype as visual reference; bulk-import assets from Strapi to Webflow's asset library.
5. Domain & DNS — staging on webflow.io first, cut over to live domain when ready.

## 7. Working patterns (carried forward from RECAP2)

- Atomic commits: one fix per commit, verified live with cache-bust before moving on.
- Integrity gate before every download: brace balance, 5/5 script tags, every script block parses via new Function(code).
- Downloads triggered from github.com origin (not raw.githubusercontent.com) and inline within the fetch callback.
- Commits verified via the GitHub API plus a SHA-pinned raw fetch before declaring done.
- Asset uploads done via GitHub web UI drag-drop into /assets/ (binary files cannot be pushed via the same download workflow).
