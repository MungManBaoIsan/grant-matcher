# Reasoning: App Build — Initial

This document captures the thinking behind the prompt. It exists so a reader can understand not just *what* the prompt is, but *why* it ended up this way.

## Goal

Get Claude to build the complete grant matching web app. But this prompt is unusual — there was no single "build this" command. The build was triggered by answering Claude's three follow-up questions after the platform choice message. The answers were the brief.

## Iteration history

Single exchange, but multi-turn. After the opening platform question, Claude asked:
- *What's your current comfort level with these technologies?* → "Mostly frontend (HTML/CSS/JS)"
- *What's your primary goal for this project?* → "Portfolio showcase piece and get actual results to help fund temple projects."
- *How complex should the AI matching be?* → "Simple keyword matching"

Those three answers were the full specification. Claude then built the complete app from them without any further instruction. The developer was aware that the answers would trigger the build — they understood the Q&A was effectively the commission.

## Failure modes the final version handles

Answering "simple keyword matching" kept the build scoped — it avoided over-engineering the matching logic at a stage where getting something working and deployed mattered more. Answering "mostly frontend (HTML/CSS/JS)" steered Claude away from proposing a backend, which would have added deployment complexity for a beginner.

## Outcome

A fully working single HTML file app — 8 real UK funders pre-loaded, 0–100% keyword match scorer, real-time results ranking, and a downloadable match report. Built and downloaded in one Claude Chat session, then deployed the same day via Claude Code.

## What I'd change next

The implicit brief worked, but being more explicit about constraints (free hosting, no login required, mobile-friendly) upfront would have saved later iteration. For a more complex project, the Q&A approach could miss things that a written spec would catch.

## Tags

`code-generation` `multi-turn` `implicit-brief` `single-file-app` `no-framework` `grant-matching` `portfolio-project`
