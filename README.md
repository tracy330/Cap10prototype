# Cap10 Website Redesign — Prototype

<img width="1764" height="805" alt="image" src="https://github.com/user-attachments/assets/6fa532a8-9554-4f53-89c8-9d486d1f8dc7" />

A clickable, single-page prototype of a refreshed Cap10 Partners website.

**Live preview:** https://tracy330.github.io/cap10-website-redesign/

*Last updated: 11 May 2026*

This prototype is intended for internal review by the partners. It is not the live Cap10 site and is not indexed by search engines. The current public site remains at https://www.cap10partners.com.

---

## Project status

The prototype phase is complete and signed off. We have now moved into production build on **Webflow** — currently **step 9 of 15 complete**. This repository remains the source of truth for the design intent and the reference the Webflow build is being matched against.

---

## Why a redesign

The current Cap10 site does an excellent job conveying who the firm is — a London-based, Western European mid-market private equity firm with large-cap heritage. Conversations with the team and feedback from partners surfaced a few opportunities the current site does not yet fully address:

- **Differentiation.** The mid-market PE category has converged on a similar visual language (dark navy, glossy stock photography, dense text). Cap10 has a distinct identity that deserves a more distinct expression.
- - **Substance over surface.** Partners want the site to communicate *how* Cap10 invests — focus, approach, and ESG framework — not only *that* Cap10 invests.
  - - **Team as a centrepiece.** The team is one of Cap10's strongest assets, but on the current site each team member is a portrait card with a name, title and a LinkedIn link. Visitors cannot read a bio without leaving the site.
    - - **Audience clarity.** Founders, CEOs and LPs all visit the site for different reasons. The prototype gives each audience a clearer, faster path.
     
      - ## What this prototype changes vs. the current site
     
      - The redesign keeps Cap10's voice and core message ("Partners in responsible change", "Western Europe, mid-market, ESG-led") and rebuilds the experience around it.
     
      - ### Visual identity
      - - A warmer, editorial aesthetic — soft cream backgrounds, deep navy primary, and a single warm accent colour replacing the cooler corporate palette.
        - - A large serif display typeface for headlines paired with a clean sans for body text — closer in feel to a thoughtful financial publication than a generic corporate site.
          - - Considered motion (subtle fades, hover states, animated section markers) used sparingly to add polish without distraction.
           
            - ### Information architecture
           
            - The current navigation (Our firm · Our team · Portfolio · Investing Responsibly · Our news · Contact) is preserved with two refinements:
            - - "Our news" is replaced with **"Insights"**, broadening the section to include articles, podcasts and thought leadership in addition to deal announcements.
              - - A persistent **"Get in touch"** call to action sits in the header on every page.
               
                - ### Homepage
                - - A full-width hero with the firm's positioning line ("Partners in responsible change") and clear primary actions: *See our portfolio* and *Meet the team*.
                  - - A new "Three promises" section (*Our focus · How we work · Why ESG matters*) that summarises Cap10's investment philosophy in three scannable cards before the visitor goes any deeper.
                    - - A selected portfolio strip surfacing flagship investments (Sureserve, Compass Community) directly on the homepage, instead of requiring a click into the portfolio page.
                      - - The Cap10 **PACCT values** (Passion, Agility, Creativity, Care, Talent) presented as a memorable graphic device rather than a paragraph.
                        - - Two clear audience entry points at the foot of the page: one for Founders & CEOs and one for Limited Partners, each leading to a tailored call to action.
                         
                          - ### Our firm
                          - - A short editorial introduction from the Founding Partner that frames the firm's purpose and origin story.
                            - - A clean separation between *what* Cap10 does and *how* Cap10 thinks — making the page easier to skim and easier to deep-read.
                              - - *Note:* The placeholder copy used on the Our Firm card in this prototype was extracted from a US investment firm's website for illustrative purposes only. It is not Cap10's own wording and must be replaced with original copy before launch.
                               
                                - ### Team — the headline change
                               
                                - On the current site, clicking a team member shows nothing more than the photo and a LinkedIn link. The prototype makes the team genuinely explorable:
                                - - **Hover** a portrait to reveal a personal quote from that team member (a small humanising touch).
                                  - - **Click** a name to open a full biography — career history, areas of focus, and the perspective they bring to Cap10.
                                    - - The team is grouped by function (Partners · Investment Team · etc.) rather than presented as a single uninterrupted grid.
                                     
                                      - ### Portfolio
                                      - - Filterable by **sector** (Essential consumer · Health & pharma · Infrastructure solutions · Niche industrials · Mission-critical business services) and by **status** (Current · Realised).
                                        - - Each company has a structured detail card: acquisition date, headquarters, sector, and a short, partner-grade narrative explaining the investment thesis and progress to date — not just a logo and a sentence.
                                         
                                          - ### Responsible investing
                                          - - A more substantive treatment of ESG, framed as a value driver rather than a compliance line.
                                            - - Concrete examples (e.g. Sureserve Foundation, decarbonising social housing) that show ESG in action across the portfolio.
                                              - - A **Regulatory Disclosure** section sits at the foot of the page, matching the page H2 style.
                                                - - A section-level CTA at the bottom of the page directs visitors to the next logical step.
                                                 
                                                  - ### Insights & Contact
                                                  - - An **Insights hub** gathering deal announcements, articles and podcasts in one place, with filter pills (*All · Deal announcements · POV · Podcast*) and a unified banner-style card layout. A media-enquiries line and a bottom CTA close the page.
                                                    - - A **Contact** experience with a form, an investor-relations email, and a bottom CTA — routing founders, CEOs and LPs to the right person rather than a single generic form.
                                                     
                                                      - ### What is intentionally not changed
                                                      - - The firm's positioning, voice, and core messaging are preserved.
                                                        - - Nav structure is largely unchanged so existing visitors are not disoriented.
                                                          - - All factual content (portfolio companies, acquisition dates, team titles) reflects the current site as of review.
                                                           
                                                            - ---

                                                            ## Recent changes

                                                            - **11 May 2026** — Fixed mojibake character encoding throughout `index.html` (em-dashes, euros, smart quotes, arrows).
                                                            - - **7 May 2026** — **"Investors login" removed** from the top nav, Contact block, and footer. The link is no longer in use.
                                                              - - **7 May 2026** — Investment Team reordered and titles updated; Neeshal portrait added.
                                                                - - **30 Apr 2026** — Added the fifth sector: **Mission-critical business services**.
                                                                  - - **30 Apr 2026** — Partners group reordered (Fabrice → Luca → Mandar → Calum) per audit.
                                                                    - - **30 Apr 2026** — Added Regulatory Disclosure section to Responsible investing; section-level CTAs added across pages.
                                                                      - - **29 Apr 2026** — Insights page redesigned with banner cards and filter pills, aligned with brand palette.
                                                                       
                                                                        - ---

                                                                        ## How to review

                                                                        1. Open https://tracy330.github.io/cap10-website-redesign/ on a desktop browser (it is also responsive on mobile).
                                                                        2. 2. Walk through each section in the top navigation: *Our firm · Team · Portfolio · Responsible investing · Insights · Contact*.
                                                                           3. 3. On the Team page, hover a portrait to see the quote, and click a name to read the full bio. A few team members (Mandar, Neeshal, Gilly) do not yet have a favourite quote — their modal will display the bio only until they share one.
                                                                             
                                                                              4. Notes, edits and corrections are welcome — please send them to Tracy directly, or open an issue on this repository.
                                                                             
                                                                              5. ## Status
                                                                             
                                                                              6. This is a design prototype, not production code. It is a single self-contained HTML file with inline CSS and JavaScript, intended to communicate intent and allow the partners to experience the redesign before any production build is commissioned. The production site is now being built in **Webflow** (step 9 of 15 complete).
                                                                             
                                                                              7. ## Repository contents
                                                                             
                                                                              8. - `index.html` — the prototype (open via the live preview link above)
                                                                                 - - `index-v1.html` / `index-v2.html` / `index-v3.html` — alternate hero-video variants of the prototype, used for stakeholder comparison
                                                                                   - - `README.md` — this document
                                                                                     - - `SESSION-RECAP.md` — running internal log of design and fix decisions across review sessions
                                                                                       - 
