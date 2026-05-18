# Reasoning: Deploy to GitHub Pages

This document captures the thinking behind the prompt. It exists so a reader can understand not just *what* the prompt is, but *why* it ended up this way.

## Goal

Deploy a completed single-file web app to GitHub Pages for the first time — making it publicly accessible as a live portfolio project. The prompt was deliberately detailed and task-numbered, leaving nothing ambiguous for Claude to interpret.

## Iteration history

One clean prompt, but the session showed real friction — `gh` wasn't found on the system path, requiring `gh auth login` to be handled manually. The deploy prompt itself didn't change; it was the environment setup that needed extra steps.

## Failure modes the final version handles

Numbering the tasks explicitly (1–8) prevented Claude from skipping steps like adding topics/tags or creating a LICENSE — details that matter for a public portfolio repo but that an open-ended prompt might omit.

## Outcome

Live at https://mungmanbaoisan.github.io/grant-matcher/. The session also taught the developer how to install and authenticate the GitHub CLI on Windows — documented in the JOURNAL.

## What I'd change next

Could add "confirm the Pages URL is returning 200" as a final verification step.

## Tags

`agent-workflow` `deployment` `github-pages` `github-cli` `real-world-use` `portfolio-project`
