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
