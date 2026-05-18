# Grant Matcher Pro

A smart web app that helps charities and community organisations discover relevant UK grant funding opportunities — and see exactly how well they match.

**Live app:** [https://mungmanbaoisan.github.io/grant-matcher/](https://mungmanbaoisan.github.io/grant-matcher/)
**GitHub:** [https://github.com/MungManBaoIsan/grant-matcher](https://github.com/MungManBaoIsan/grant-matcher)

## What It Does

- Enter your organisation's profile and keywords to get personalised grant matches
- Scores 8+ UK funders (National Lottery, Esmée Fairbairn, and more) from 0–100% match
- Ranks results in real time so the best funding fits rise to the top
- Export a detailed match report to support your grant applications
- Works on desktop, tablet, and mobile — no installation needed

## Built With

- **HTML** — the structure and content of the page
- **CSS** — styling, layout, and the gradient design
- **JavaScript (Vanilla)** — the matching algorithm and all interactive features
- **localStorage** — saves your profile in the browser so nothing is lost on refresh
- **GitHub Pages** — free hosting that makes the app live on the internet

## How to Run It

1. Visit the live app: [https://mungmanbaoisan.github.io/grant-matcher/](https://mungmanbaoisan.github.io/grant-matcher/)
2. Or clone it locally:
   ```
   git clone https://github.com/MungManBaoIsan/grant-matcher.git
   ```
3. Open `index.html` in your browser — no setup or build process needed

## My Journey

**18 May 2026 — Ran prompt evaluations, fixed UTF-8 bug, confirmed CI passing on GitHub**

I ran the eval runner for the first time, hit a few snags (missing `prompt.md` files, a Windows encoding crash when writing emoji), and fixed them. Created fixture files for all 5 prompts so the CI can run deterministically without API calls. All 5 prompts now score 100% in mock mode. The GitHub Actions workflow confirmed green — from now on every push to the prompts folder triggers an automatic check.

**18 May 2026 — Added prompt archive with reasoning docs, rubrics, and CI eval workflow**

I documented the 5 prompts used to build this project and organised them into a `/prompts` folder — each with a `REASONING.md` explaining the thinking and a `rubric.yaml` with testable pass conditions. I also added an eval runner script and a GitHub Actions CI workflow that checks every prompt automatically on each push. One prompt was labelled "reconstructed" because the original lived in Claude Chat with no recoverable logs — being honest about that matters. I also learned that Claude Code session logs are stored as `.jsonl` files that you can grep to recover real verbatim prompts from past sessions.

**16 May 2026 — Deployed Grant Matcher Pro to GitHub Pages**

I built and deployed Grant Matcher Pro — a single-page web application that helps charities and community organisations find relevant UK grant funding. The app lets users enter their organisation's profile and keywords, then scores and ranks a pre-loaded database of 8+ UK funders by match percentage.

I built it as a single HTML file (no frameworks, no build tools) so it runs instantly in any browser and deploys to GitHub Pages with zero configuration. The JavaScript matching algorithm compares keywords from the user's profile against each grant's criteria, scores them 0–100%, and ranks them in real time.

I also learned how to install and use the GitHub CLI on Windows, create a public repository from the terminal, and enable GitHub Pages — all in a single session.

## What's Next

- Add a backend database so new grants can be added without editing the code
- Integrate Claude API for smarter semantic matching (not just keywords)
- Add email alerts when new grants match your organisation's profile
