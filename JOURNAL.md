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
