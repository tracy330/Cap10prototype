# SESSION RECAP 2 — Cap10 Website Redesign

**Date:** 30 April 2026
**Repo:** `tracy330/cap10-website-redesign`
**Live site:** https://tracy330.github.io/cap10-website-redesign/

---

## Overview

This session covered three blocks of work, in order:

1. **Three missing items added** from the original cap10partners.com site that were not yet in the prototype.
2. **Full content audit** of all seven pages of the prototype against the original site, page by page.
3. **Audit fixes applied** as ten atomic commits, then the three video variants rebuilt from the new baseline.

The prototype URL did not change. All work landed on `main` and was verified live.

---

## Part 1 — Three missing items added

### 1. Fifth sector card: Mission-critical business services (`512362a`)

The original site listed five sectors in prose; the prototype had elevated four into cards. The fifth, **Mission-critical business services** (abbreviation **Mb.**), was added as a fifth card with copy in the same editorial voice as the others. The supporting prose, the H2 heading, and four other prose mentions were updated for consistency.

### 2. Regulatory Disclosure block on Responsible Investing (`1e5cdf4`)

A Regulatory Disclosure block was added at the bottom of the Investing Responsibly page, with two amber bullet links:
- **MIFIDPRU 8 disclosures** — https://cms.cap10partners.com/uploads/Mi_FIDPRU_8_Disclosure_41f3ffa4df.pdf
- **Responsible Investment Policy — View policy** — https://cms.cap10partners.com/uploads/Cap10_Responsible_Investment_Policy_with_appendix_update_19_Feb_2026_24848f9271.pdf

### 3. Heading style fix on the Regulatory Disclosure block (`57e2c7f`)

The H2 was rendering near-black instead of the page's teal/ink token. Style was matched to the page's other H2s (Fraunces serif, `color:var(--ink)`, `font-size:clamp(28px,3.2vw,42px)`).

---

## Part 2 — Page-by-page audit (read-only)

The original cap10partners.com site was opened in a parallel tab and each page was compared against the prototype. Findings were grouped into three buckets per page: **confirmed matches**, **intentional redesign differences**, and **genuine discrepancies**. No prototype changes were made during the audit phase.

Pages audited:
- Homepage
- Our firm
- Team
- Portfolio
- Responsible investing
- Contact
- Insights / News

---

## Part 3 — Audit fixes applied (10 atomic commits)

| # | Fix | Commit |
|---|---|---|
| 1 | Remove \"Thirteen investors and operators...\" line from Our Firm | `a2bbd3e` |
| 2 | Reorder Partners group on Team page — Mandar before Calum | `b0b5e7f` |
| 3 | Revert Portfolio \"How we invest\" copy to original (valuation, not enterprise value) | `95b5139` |
| 4 | Soften \"Where our portfolio meets\" copy on Responsible Investing — Compass & Sureserve are in early conversations about whether care leavers might benefit from the apprenticeship programme | `e4f26d4` |
| 5 | Restore paragraph break in Responsible Investing intro | `4dc45d4` |
| 6 | Add bottom \"Interested in partnering with us? — Contact us\" CTA on Responsible Investing | `35560be` |
| 7 | Contact page: add styled contact form (Name / Surname / Email / Message / Submit, mailto:corporate@cap10partners.com); set IR card email to ir@cap10partners.com; add bottom CTA | `77542ae` |
| 8 | Insights: add \"For media enquiries, please email corporate@cap10partners.com\" line and bottom CTA | `92955a1` |
| 9 | Add \"Investors login\" link to top nav (opens icx.efrontcloud.com investor portal in new tab) | `751d1e1` |
| 10 | Footer: revert \"Terms\" → \"Terms & Conditions\"; add \"Investors login\" link in footer (visible from every page) | `16e1ba1` |

Note: commit `16e1ba1` reused the previous commit's message label ("Add Investors login link to top nav") because the GitHub upload form retained it. The actual content of `16e1ba1` is the footer fix as listed in row 10. The repo end state is correct; only the message label is mislabelled.

---

## Part 4 — Three video variants rebuilt from the new baseline

After the audit fixes were complete, the three video variant files were rebuilt from the latest `16e1ba1` baseline so each carries all today's audit fixes plus a different hero clip. Hero clips remain autoplaying, muted, looping `<video>` elements; only the `<source src>` URL differs per file.

| File | Hero clip | Final commit |
|---|---|---|
| `index-v1.html` | Mixkit wind turbine — https://assets.mixkit.co/videos/34102/34102-720.mp4 | `d1d2d8a` |
| `index-v2.html` | Mixkit solar panel — https://assets.mixkit.co/videos/23491/23491-720.mp4 | `ce52b2e` |
| `index-v3.html` | Mixkit coastal aerial — https://assets.mixkit.co/videos/1955/1955-720.mp4 | `69896b2` |

Two re-uploads were needed — one for v2 and one for v3 — because the first uploads landed as 9-byte `undefined` placeholder files (caused by the JS variable being wiped between download trigger and click). The final live files are full size (~516 KB) and verified.

---

## Final state — verified live

| File | Size | Hero | All 10 audit fixes |
|---|---|---|---|
| `index.html` | 516,055 bytes | Original CMS clip | ✅ |
| `index-v1.html` | 516,034 bytes | Mixkit wind turbine | ✅ |
| `index-v2.html` | 516,034 bytes | Mixkit solar panel | ✅ |
| `index-v3.html` | 516,032 bytes | Mixkit coastal aerial | ✅ |

Each variant was checked with twelve presence assertions covering all ten audit fixes (no \"Thirteen investors\" line, Mandar before Calum, original Portfolio copy, softened RI block, paragraph break, three CTAs, contact form, ir@ email, media enquiries line, nav investors login, Terms & Conditions, footer investors login).

---

## Decisions captured during this session

These were made during the audit and applied via the fix list:

- Five-sector cards (Ni / Es / Hp / In / Mb) are an **intentional redesign elevation** of the original prose. Stays.
- Tigran Petrosyan as **Managing Director**, Joe Baxter as **Director**, and the **Neeshal Rao** and **Gilly Adcock** additions are **correct**.
- Mandar Kulkarni's role string stays as **\"Partner, CFO & COO\"** with ampersand.
- Partners group order is **Fabrice → Luca → Mandar → Calum** (Mandar before Calum because he was a Partner first).
- Portfolio \"How we invest\" wording stays as the **original valuation phrasing**, not the prototype's \"enterprise value\" rewrite.
- The \"Where our portfolio meets\" Compass × Sureserve block is **exploratory framing**, not a finished programme — they are in early conversations about whether care leavers might benefit from Sureserve's apprenticeship programme.
- The Responsible Investing intro is **two paragraphs**, not one, matching the original.
- Each major section page (Responsible investing, Contact, Insights) carries its own bottom **\"Interested in partnering with us? — Contact us\"** CTA in addition to the global Contact CTA.
- Contact page keeps the **\"I'm an institutional investor\"** card, the **\"Investors login\"** tile, and now also a **styled contact form** that submits via `mailto:corporate@cap10partners.com`.
- IR email is **`ir@cap10partners.com`**.
- Media enquiries email is **`corporate@cap10partners.com`** (no separate press address).
- \"Read more →\" affordance on Insights cards was **not added** — current card design preferred.
- \"Investors login\" appears in **both top nav and footer** so it's reachable from every page.
- Footer reads **\"Disclaimer · Cookie policy · Terms & Conditions · Investors login\"** on every page.

---

## Outstanding / next session

- No outstanding fixes from the audit.
- Three video variants are live for side-by-side comparison; final selection of the preferred hero clip can be made in a future session.
- If a server-side handler is later wanted for the Contact form (Formspree, Netlify Forms, etc.), that can be wired up to replace the current `mailto:` action.
- Commit `16e1ba1` has a mismatched message label ("Add Investors login link to top nav" instead of describing the footer change). Cosmetic only; can be amended via `git commit --amend` locally if desired.
