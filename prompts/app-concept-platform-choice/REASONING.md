# Reasoning: App Concept & Platform Choice

This document captures the thinking behind the prompt. It exists so a reader can understand not just *what* the prompt is, but *why* it ended up this way.

## Goal

Figure out the right tool/platform to build a grant-matching database or AI tool before writing a single line of code. The prompt was a deliberate strategic question — "would this be better done on Claude Chat, Claude Cowork or Claude Code?" — rather than jumping straight into building.

## Iteration history

This was the opening move of the whole project. The answer (Claude Code) then kicked off the full build session. So this prompt is the root of the entire Grant Matcher Pro app.

## Failure modes the final version handles

By asking about platform choice first, the prompt avoids the common beginner mistake of starting to build in the wrong environment and having to start over. The framing as a "quick question" also signals the user wanted a direct recommendation, not a long comparison essay.

## Outcome

The answer pointed to Claude Code. The full Grant Matcher Pro app was built in a single session as a result — a single-file HTML/CSS/JS app deployed to GitHub Pages.

## What I'd change next

Could add constraints like "I want it to work without a backend" or "I want to deploy it for free" — that context would have made the platform recommendation even more targeted.

## Tags

`analysis` `architecture-decision` `tool-selection` `beginner-developer` `pre-build-planning`
