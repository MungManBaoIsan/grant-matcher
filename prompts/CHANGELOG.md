# Prompt Changelog

Chronological record of prompt creation. Newest entries at the top.

---

## grant-application-writer

### 2026-01-12 — v1
**Change:** Initial version.
**Reason:** Needed a professional grant application for the Buddhapadipa Temple Trust's Thai Language for All project — a real £50,000 funding bid, not a practice exercise.
**Impact:** Output was submitted, adapted, and used. Later repurposed as the test case when building Grant Matcher Pro.

---

## deployment-strategy-request

### 2026-05-18 — v1
**Change:** Initial version. Added from second conversation review.
**Reason:** Captured the meta-prompt technique used to commission the Claude Code deployment prompt — using Claude Chat to generate input for Claude Code rather than writing it manually.
**Impact:** Claude generated a complete, structured Claude Code prompt from project context already in the conversation. Pasted and executed successfully in Claude Code.

---

## app-concept-platform-choice

### 2026-05-18 — v1 (corrected)
**Change:** Removed inaccurate "Quick question:" prefix from prompt text. Updated REASONING.md to correct an error — previous version stated the app was built in Claude Code; it was actually built entirely in Claude Chat. Also updated REASONING.md to reflect that the prompt was natural rather than strategic.
**Reason:** Conversation log review revealed the original archive was slightly inaccurate.
**Impact:** Record now accurately reflects what happened.

### 2026-05-16 — v1
**Change:** Initial version.
**Reason:** Needed to choose the right Claude environment before writing a single line of code — Claude Chat, Cowork, or Code.
**Impact:** Claude responded with an architecture overview and Q&A questions that scoped the entire build.

---

## app-build-initial

### 2026-05-18 — v1 (updated from reconstructed)
**Change:** Replaced reconstructed single-command prompt with the actual multi-turn Q&A exchange that triggered the build. Removed "Reconstructed" label. Updated REASONING.md to reflect that the developer understood their Q&A answers would commission the app.
**Reason:** Conversation log review revealed the original was a plausible but fictional reconstruction. The real build brief was three Q&A answers.
**Impact:** Archive now accurately reflects the actual build process.

### 2026-05-16 — v1 (reconstructed)
**Change:** Initial version.
**Reason:** Needed a complete, deployable grant matching web app with no build tools or dependencies — a single HTML file that could go straight to GitHub Pages.
**Impact:** Produced the full Grant Matcher Pro app in one exchange. Downloaded and deployed the same day.

---

## deploy-to-github-pages

### 2026-05-16 — v1
**Change:** Initial version.
**Reason:** First-time GitHub Pages deployment on Windows — needed every step listed explicitly so nothing was missed (repo creation, .gitignore, LICENSE, Pages config, topics).
**Impact:** App live at https://mungmanbaoisan.github.io/grant-matcher/. Session also taught gh CLI authentication on Windows.

---

## portfolio-update

### 2026-05-16 — v1
**Change:** Initial version.
**Reason:** Document the completed project immediately after deployment — same session, no delay between shipping and recording.
**Impact:** Grant Matcher Pro added to portfolio with both URLs, tech stack, and key features.

<!-- Add new entries above as prompts are iterated or added. -->
