Cap10 Website Redesign — Session Recap
File: SESSION-RECAP.md
Last updated: 29 April 2026
Repository
tracy330/cap10-website-redesign — https://github.com/tracy330/cap10-website-redesign
Live preview: https://tracy330.github.io/cap10-website-redesign/
Session 1 — 28 April 2026 (yesterday)
Goal: Fix the team bio modal so each team member's card opens their own bio (rather than every card showing Fabrice Nottin's content).
Approach:

Added onclick="cap10ShowBio('member-id')" handlers to each team member card.
Modified the cap10ShowBio function to dynamically populate the modal with the clicked member's name, role, photo, pull quote, attribution, and bio text.

Outcome: Reported as working at the time, but introduced a JavaScript syntax error (one missing closing brace }) in the script block at the bottom of index.html. The error was undetected because the navigation wasn't tested after the commit. Bug entered the file in commit f9f28c0 (28 April, 14:51:52 UTC).
Session 2 — 29 April 2026 (today)
Issues discussed:

Underline appearing on "responsible change" in the homepage hero H1.
Need to research alternative hero strap imagery/video aligned with the redesign direction.

Visual research — four pillars proposed:

Pillar 1: Energy transition / infrastructure in motion (wind, solar, retrofit) — being prototyped first.
Pillar 2: Operational craft and people (technicians, engineers on site).
Pillar 3: European industrial landscape (cinematic stills/B-roll) — being prototyped second.
Pillar 4: Abstract/textural loops for hero backgrounds.

Decision: Build three prototype variants on main so partners can compare side-by-side via stable GitHub Pages URLs.
Stock video sourcing: Pexels was blocked on the user's network. Switched to Mixkit (mixkit.co) — free licence, commercial use permitted, 720p MP4 hosted on Mixkit's CDN. Sourced three clips:

v1 — drone wind turbine (Mixkit ID 34102)
v2 — solar panel installation (Mixkit ID 23491)
v3 — coastal aerial landscape (Mixkit ID 1955)

Files created on main:

index-v1.html (renamed from Index-v1.html to fix Linux case-sensitivity)
index-v2.html
index-v3.html

Bug discovered: All four files (index.html, index-v1.html, index-v2.html, index-v3.html) failed to render correctly. Symptoms: text missing, navigation links not clickable, two bio modals stacking on top of each other.
Root-cause analysis:

Browser console showed SyntaxError: Unexpected token ')' at line 1460.
Script block at the bottom of index.html had 28 opening braces vs 27 closing braces — one extra { left unclosed since commit f9f28c0 from 28 April.
Additional contributing factor: when committing the underline fix earlier today, the commit message text ("Remove .h1 u amber underline rule from homepage hero") was accidentally typed into the bottom of the file body instead of the commit dialog. This was due to unclear instructions about where the commit form lives in GitHub's modern UI.

Resolution: Reverted index.html on main to commit afe0552 (28 April, 14:49:48 UTC) — the last known-working state, which has 67 balanced braces and 1,561 lines. Commit 4043d0e performed the revert.
State after revert:

✅ Page routing works on all nav links (Our firm, Team, Portfolio, Responsible investing, Insights, Contact, back to home via Cap10 logo).
✅ JavaScript parses cleanly (verified: 67 open / 67 close braces in script block).
❌ Team bio modal shows Fabrice's content stacked on top of every clicked member's content (same pre-fix bug as before Session 1).
❌ Character-encoding glitches throughout the site (e.g. ÃÂÃÂ¢ÃÂÃÂÃÂÃÂ appearing where em-dashes should be — visible in page titles and the "Favourite quote" attribution).
❌ Insights and Contact page cards need style/colour alignment with rest of design system.
❌ The three Mixkit video variants (index-v1.html, index-v2.html, index-v3.html) still contain the broken f9f28c0-era script and need to be re-built from the working base.

Outstanding work — next session
In recommended order (each item should be its own commit, verified before moving on):

Glitch / character-encoding fix — find and replace corrupted Unicode sequences throughout index.html. Easiest to verify, lowest risk.
Insights & Contact card alignment — CSS-only changes to bring those cards into the design system (colour tokens, typography, spacing). Pure styling, can't break JS.
Team-bio modal re-fix — restore the per-member modal logic carefully, with brace-balance verified before committing. This is the one to be most cautious with given prior history.
Re-create index-v1.html, index-v2.html, index-v3.html — copy the now-clean index.html three times, swapping in the three Mixkit video URLs:

v1: https://assets.mixkit.co/videos/34102/34102-720.mp4
v2: https://assets.mixkit.co/videos/23491/23491-720.mp4
v3: https://assets.mixkit.co/videos/1955/1955-720.mp4



Key working commit references

afe0552 — last known fully-working index.html (28 April, 14:49:48 UTC). Trusted baseline. 1,561 lines, 67/67 balanced braces.
4043d0e — today's revert commit on main that restored the working baseline.
f9f28c0 — the commit that introduced the syntax error (28 April, 14:51:52 UTC). Avoid reverting to this; only useful as a marker for when things broke.

Lessons learned

Test navigation/console after every commit that touches JavaScript. The bug went undetected for a full day because no one clicked through the nav after Session 1's commits.
Never type commit messages or notes inside the file editor body. GitHub's modern UI puts the commit form in a pop-up dialog that opens after clicking the green "Commit changes…" button at the top-right.
Track brace balance explicitly when editing JavaScript blocks. Even one missing brace silently destroys the entire script.
Keep changes atomic. One fix per commit, verified before moving to the next. Big multi-fix commits are where regressions hide.

Useful URLs

Repo: https://github.com/tracy330/cap10-website-redesign
Live (always shows main): https://tracy330.github.io/cap10-website-redesign/
Variant previews (once rebuilt): …/index-v1.html, …/index-v2.html, …/index-v3.html
File commit history: https://github.com/tracy330/cap10-website-redesign/commits/main/index.html
Working baseline file: https://raw.githubusercontent.com/tracy330/cap10-website-redesign/afe0552/index.html
