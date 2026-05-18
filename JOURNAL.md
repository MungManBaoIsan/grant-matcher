# Development Journal — Grant Matcher Pro
A chronological log of key developments, decisions and learnings throughout this project.

---

## 16 May 2026 — Deployed Grant Matcher Pro to GitHub Pages

**Type:** Milestone

**What I built or did**
I built and deployed Grant Matcher Pro — a single-page web application that helps charities and community organisations find relevant UK grant funding. The app lets users enter their organisation's profile and keywords, then scores and ranks a pre-loaded database of 8+ UK funders (including the National Lottery Community Fund and Esmée Fairbairn Foundation) by match percentage. I also deployed it live using GitHub Pages.

**Why I did it this way**
I built it as a single HTML file (no frameworks, no build tools) so it runs instantly in any browser and deploys to GitHub Pages with zero configuration. This was the right choice for a portfolio project — it keeps the focus on the logic and UI without adding unnecessary complexity.

**How it works**
The JavaScript matching algorithm compares keywords from the user's organisation profile against each grant's criteria. It scores each funder from 0–100% and ranks them in real time. Users can then export a match report. All data is stored client-side using the browser's localStorage.

**What this means for the app**
The app is fully live and accessible to anyone — a real, working tool that could genuinely help small nonprofits discover funding they might otherwise miss. It's also a strong portfolio piece showing I can build and ship a complete web project independently.

**What I learned**
I learned how to install and authenticate the GitHub CLI (`gh`) on Windows, create a public repository from the terminal, push files to GitHub, and enable GitHub Pages — all from scratch in a single session. I also learned the difference between bash and PowerShell when running CLI tools on Windows.

**References / Conversations**
Built and deployed with Claude Code in one session (May 2026).

---

## 18 May 2026 — Added prompt archive with reasoning docs, rubrics, and CI eval workflow

**Type:** Milestone

**What I built or did**
I documented the 5 prompts used to build Grant Matcher Pro and organised them into a structured `/prompts` folder. Each prompt has a `REASONING.md` file explaining the thinking behind it and a `rubric.yaml` file with testable pass conditions. I also added an eval runner script (a Python tool that scores prompt outputs against the rubric) and a GitHub Actions CI workflow (an automated process that checks the prompts on every push).

**Why I did it this way**
I used the `prompt-archivist` skill to run the whole process — scanning for prompts, interviewing myself about the reasoning, reviewing drafts, then writing files. This approach means every prompt has a documented *why*, not just a *what*. I also labelled one prompt as "reconstructed" because the original was sent in Claude Chat with no recoverable logs — being honest about that matters.

**How it works**
The `/prompts` folder contains one subfolder per prompt. Each has a `REASONING.md` capturing goal, iteration history, failure modes, and outcome — plus a `rubric.yaml` with criteria that can be evaluated automatically. The `scripts/eval_runner.py` runs those criteria against model outputs and exits with a non-zero code if any prompt scores below 80%.

**What this means for the app**
The prompts folder adds portfolio value to the repo — it shows not just that I built the app, but how I thought through each step. Hiring managers and collaborators can see the reasoning behind the build, the deployment, and the grant writing that informed it.

**What I learned**
I learned that Claude Code session logs are stored as `.jsonl` files in `~/.claude/projects/` — and that with the right grep, you can recover actual verbatim prompts from past sessions. I also learned that some prompts live in Claude Chat (no logs), some in Claude Code (recoverable), and being clear about which is which matters for honest documentation.

**References / Conversations**
Archived using the `prompt-archivist` skill in a Claude Code session (May 2026). Session log: `C--Users-joshk-grant-matcher/609ce33a...jsonl`.

---

## 18 May 2026 — Ran prompt evaluations, fixed UTF-8 bug, confirmed CI passing on GitHub

**Type:** Bug Fix / Milestone

**What I built or did**
I ran the prompt eval runner (a Python script that checks each prompt against its rubric) for the first time. It failed initially because the prompt directories were missing `prompt.md` files — the runner needs those to find and load each prompt. I created minimal `prompt.md` files for all 5 prompts, then created fixture files (sample outputs that the mock mode tests against) for each one. I also hit a Windows-specific bug where the runner crashed trying to write emoji characters — fixed by adding `encoding='utf-8'` to the file writer.

**Why I did it this way**
Fixtures are the right approach for CI testing because they let the eval runner check rubrics without calling the Claude API on every push — fast, free, and deterministic (meaning it gives the same result every time). Each fixture is a representative sample output that passes all the rubric criteria.

**How it works**
The runner looks for a `prompt.md` and `rubric.yaml` in each prompt directory. For each test case in the rubric, it looks up a fixture file by fingerprint (a code generated from the test inputs), loads that as the model output, then evaluates each pass condition against it. If any prompt scores below 80%, the whole run fails.

**What this means for the app**
The GitHub Actions CI workflow (an automated check that runs on every push) is now fully wired up and confirmed green. From this point on, any change to the prompts folder will automatically trigger a lint and eval check — broken rubrics or missing files will be caught before they reach the main branch.

**What I learned**
I learned that Claude Code session logs are stored as `.jsonl` files and you can extract real verbatim prompts from them using PowerShell. I also learned that Windows uses a different default text encoding (cp1252) to Linux, which causes crashes when writing emoji — always specify `encoding='utf-8'` when writing files in Python on Windows.

**References / Conversations**
Full session in Claude Code (18 May 2026). CI confirmed passing via `gh run list`.

---

## 18 May 2026 — Audited prompt archive against source conversations; added meta-prompt entry

**Type:** Improvement / Documentation

**What I built or did**
I went back to the original Claude Chat conversations where Grant Matcher Pro was built and cross-checked them against the existing prompt archive. The project was built across *two* separate conversations — a January session where I wrote the Buddhapadipa Temple grant application, and a May session where I built, deployed, and documented the app itself. I had to consider both when deciding what to update.

The January conversation (shared at the same link) was only partly recoverable — Firecrawl could extract Claude's responses but the user messages were hidden because the shared view doesn't expose file attachments. So `grant-application-writer` was left as-is: we couldn't verify the original prompt, so making changes would have meant guessing.

For the May conversation I found and corrected two inaccuracies and added a new prompt that wasn't captured first time round.

For `app-concept-platform-choice`, the reasoning doc incorrectly stated that the app was built in Claude Code — it was built entirely in Claude Chat. Claude Code was only used later for deployment. I also removed a "Quick question:" prefix from the prompt text that wasn't in the original.

For `app-build-initial`, the first archive had a reconstructed single-command prompt that was never actually sent. The real build was triggered by answering three Q&A questions from Claude — about my tech comfort level, project goals, and matching complexity. I replaced the reconstruction with the actual Q&A exchange.

I also added `deployment-strategy-request`, a new prompt that captures a technique I used without naming it at the time: asking Claude Chat to *write* a prompt for Claude Code rather than writing it myself. Because Claude already had all the project context in the conversation, it generated an accurate, detailed Claude Code deployment brief without me having to re-explain anything.

**Why I did it this way**
The first archive was done from memory — close, but not verbatim. Going back to the actual conversation and correcting what was wrong is more honest and more useful as portfolio evidence. A prompt archive that labels reconstructions correctly, and updates them when source material becomes available, is more trustworthy than one that leaves plausible-but-fictional descriptions in place.

**How it works**
I used the `prompt-archivist` skill — fetching the shared link with Firecrawl, pasting the conversation content directly (user messages aren't rendered in shared views), running the interview phase, reviewing each REASONING.md draft inline before writing anything, then updating the index README and CHANGELOG. All six prompts pass the mock eval at 100%.

**What this means for the app**
The prompt archive is now sourced from the actual conversation rather than reconstruction. Two existing prompts corrected, one updated to reflect its real multi-turn format, one new prompt added. The CHANGELOG records all of this with before/after entries — so the correction history is part of the portfolio story, not hidden.

**What I learned**
Claude.ai shared links don't expose user messages in a way that standard web fetch tools can read — the page is JavaScript-rendered. Firecrawl can get Claude's responses, but for the user's actual prompts you need to paste directly from the original conversation. Also: correcting a prompt archive when source material becomes available is worth doing even if the reconstruction was close — accuracy matters more than consistency.

**References / Conversations**
Source conversation: https://claude.ai/share/3ef96091-978a-4247-8f45-9b08d78a270a (16 May 2026 — the original Grant Matcher Pro build session in Claude Chat).

---
