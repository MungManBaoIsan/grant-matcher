# Reasoning: App Concept & Platform Choice

This document captures the thinking behind the prompt. It exists so a reader can understand not just *what* the prompt is, but *why* it ended up this way.

## Goal

Figure out the right tool to use for building a grant-matching database or AI tool before writing any code. Not a deliberate strategy — it came naturally at the start of the conversation, which is worth noting honestly. The framing ("Would this be better done on Claude Chat, Claude Cowork or Claude Code?") shows a beginner instinctively asking the right question even without knowing to call it architecture planning.

## Iteration history

Single version. This was the opening message of the whole project. No refinement — the question was typed out and sent as-is.

## Failure modes the final version handles

By asking about platform choice first, the prompt avoided starting to build in the wrong environment. In practice, Claude responded with a full breakdown of options and asked 3 follow-up Q&A questions — so the short prompt generated a much deeper scoping conversation than a longer, more prescriptive prompt might have.

## Outcome

Claude responded with an architecture overview and three Q&A questions about tech comfort, project goals, and matching complexity. The answers to those questions then triggered the actual app build — all within Claude Chat. (Note: the app was built entirely in Claude Chat, not Claude Code. Claude Code was only used later for deployment.)

## What I'd change next

Adding constraints upfront — like "I want it to work without a backend" or "I want to deploy it for free" — would have made the recommendation even more targeted and skipped the Q&A round.

## Tags

`analysis` `architecture-decision` `tool-selection` `beginner-developer` `pre-build-planning`
