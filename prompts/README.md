# Prompt Library — Grant Matcher Pro

[![Prompt Eval](https://github.com/MungManBaoIsan/grant-matcher/actions/workflows/prompt-eval.yml/badge.svg)](https://github.com/MungManBaoIsan/grant-matcher/actions/workflows/prompt-eval.yml)

This folder documents the prompts used to build Grant Matcher Pro. It exists as portfolio evidence of prompt engineering, evaluation, and iteration — not as runtime configuration.

Each prompt directory contains the reasoning behind it and an executable evaluation rubric. Every rubric runs on every push via GitHub Actions.

## Index

| Prompt | Category | What it does | Source |
|---|---|---|---|
| [`grant-application-writer`](./grant-application-writer/) | content | Writes a 750-word professional grant application for real submission | Real |
| [`app-concept-platform-choice`](./app-concept-platform-choice/) | analysis | Recommends the right Claude platform before any code is written | Real |
| [`app-build-initial`](./app-build-initial/) | code-generation | Builds the complete single-file grant matching web app via Q&A answers | Real (multi-turn) |
| [`deployment-strategy-request`](./deployment-strategy-request/) | agent-workflow | Uses Claude Chat to generate a Claude Code deployment prompt (meta-prompt) | Real |
| [`deploy-to-github-pages`](./deploy-to-github-pages/) | agent-workflow | Creates GitHub repo, commits files, and enables GitHub Pages | Real |
| [`portfolio-update`](./portfolio-update/) | agent-workflow | Adds the completed project to the developer's portfolio | Real |

## Featured iterations

### [`app-concept-platform-choice`](./app-concept-platform-choice/)

The whole project started with a single instinctive question before any code was written: *"Would this be better done on Claude Chat, Claude Cowork or Claude Code?"* This prompt shows a beginner developer asking the right question even without knowing to call it architecture planning. The short prompt generated a full scoping conversation — Claude responded with options and three Q&A questions that shaped the entire build.

### [`app-build-initial`](./app-build-initial/)

There was no explicit "build this" command. The app was commissioned by answering three Q&A questions from Claude — tech comfort level, project goals, and matching complexity. Those answers were the full specification. This shows how a multi-turn conversation can function as a build brief, and how deliberate answers to scoping questions steer the output without writing a formal spec.

### [`deployment-strategy-request`](./deployment-strategy-request/)

A meta-prompt: using Claude Chat to generate a prompt for Claude Code. Rather than writing the Claude Code prompt from scratch, this prompt asked Claude Chat (which already had the full project context) to produce the deployment brief. The generated prompt was then pasted directly into Claude Code and executed successfully.

### [`deploy-to-github-pages`](./deploy-to-github-pages/)

The deployment prompt demonstrates deliberate prompt structure: 8 explicitly numbered tasks so nothing gets skipped, plus additional setup requirements listed separately. The session hit real friction (`gh` not found on the system path) — the prompt held up; the environment needed fixing first.

## Skills demonstrated

- [x] **Prompt design** — every prompt has a documented goal and structure
- [x] **Evaluation** — every prompt has a rubric with executable pass conditions
- [x] **Automated testing** — rubrics run on every push via [`prompt-eval.yml`](../.github/workflows/prompt-eval.yml)
- [x] **Documentation** — every prompt has a REASONING.md explaining the *why*
- [x] **Honest labelling** — reconstructed prompts are clearly marked as such

## Running the evaluations locally

```bash
# Install dependency
pip install pyyaml

# Dry run — validates rubric structure only, no LLM calls
python scripts/eval_runner.py --dry-run

# Mock run — runs rubrics against fixture files, no API cost
python scripts/eval_runner.py --provider mock

# Real run — calls Claude API (requires ANTHROPIC_API_KEY)
python scripts/eval_runner.py --provider anthropic

# Run a single prompt only
python scripts/eval_runner.py --prompt deploy-to-github-pages --provider mock
```

See [`CHANGELOG.md`](./CHANGELOG.md) for the prompt evolution story.
