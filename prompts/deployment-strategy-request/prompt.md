# Deployment Strategy Request

> **Category:** agent-workflow | **Status:** production | **Last updated:** 2026-05-18

## What this prompt does

Asks Claude Chat to generate two things at once: step-by-step GitHub Pages deployment instructions, and a ready-to-paste prompt for Claude Code to execute the deployment automatically. This is a meta-prompt — using one AI session to generate input for another.

## The prompt

```
Can we do this:
1. How to Deploy (Make it Live): Option 1: Quick & Free (GitHub Pages)
2. Write a prompt for Claude Code to use portfolio-update skill to add it Grant Matcher Application Project to GitHub.
```

## Inputs

- Implicit context from the conversation: project name (grant-matcher), files (index.html, README.md), GitHub username
- Implicit context: developer has a portfolio-update skill set up in Claude Code

## Expected output

- Numbered manual deployment steps for GitHub Pages (create repo, upload files, enable Pages)
- A formatted, ready-to-paste Claude Code prompt containing: repo name, file list, numbered tasks, GitHub Pages setup, and portfolio-update skill invocation
- Manual fallback instructions in case Claude Code cannot handle it

## Related files

- Reasoning: [`REASONING.md`](./REASONING.md)
- Evaluation rubric: [`rubric.yaml`](./rubric.yaml)
