# App Build — Initial

> **Category:** code-generation | **Status:** production | **Last updated:** 2026-05-18
> **Note:** Multi-turn — the build was triggered by answering Claude's Q&A questions, not a single command.

## What this prompt does

Commissions a complete grant matching web app by answering three targeted Q&A questions from Claude about tech comfort, project goals, and matching complexity.

## The prompt

This was a multi-turn exchange. After the platform choice question, Claude asked three follow-up questions. The answers below constitute the full build brief:

**Q: What's your current comfort level with these technologies?**
A: Mostly frontend (HTML/CSS/JS)

**Q: What's your primary goal for this project?**
A: Portfolio showcase piece and get actual results to help fund temple projects.

**Q: How complex should the AI matching be?**
A: Simple keyword matching

## Inputs

No structured inputs — the Q&A context was implicit from the preceding platform choice conversation.

## Expected output

A complete single-file HTML/CSS/JS web application with:
- Organisation profile form
- UK grant database (8+ funders)
- Keyword-based matching algorithm with 0–100% scores
- Ranked results dashboard
- Export/download functionality

## Related files

- Reasoning: [`REASONING.md`](./REASONING.md)
- Evaluation rubric: [`rubric.yaml`](./rubric.yaml)
