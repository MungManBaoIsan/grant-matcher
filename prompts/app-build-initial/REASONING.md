# Reasoning: App Build — Initial (Reconstructed)

This document captures the thinking behind the prompt. It exists so a reader can understand not just *what* the prompt is, but *why* it ended up this way.

## Goal

Build a functional grant matching web app as a single HTML file — a clean, foundational tool that could be improved later. Based on the code, the prompt asked for a complete app with a profile form, keyword-based matching algorithm, a pre-loaded UK grant database, and export functionality, all styled with a professional design.

## Iteration history

Reconstructed. The original build prompt was sent in Claude Chat (not Claude Code) and no session log exists. The app was built in one exchange and downloaded as a complete file before being deployed via Claude Code. The developer's own account: "a basic build for a solid foundational app that could be improved later."

## Failure modes the final version handles

By targeting a single HTML file with no frameworks or build tools, the prompt avoided the common trap of over-engineering a beginner portfolio project — nothing to install, nothing to configure, and deploys to GitHub Pages for free.

## Outcome

A fully working app with 8 real UK funders pre-loaded, a 0–100% keyword match scorer, real-time results ranking, and a downloadable match report. Deployed live the same day.

## What I'd change next

As noted in the README — add a backend database, integrate Claude API for semantic matching (not just keywords), and add email alerts for new grant matches.

## Tags

`code-generation` `single-file-app` `no-framework` `reconstructed` `grant-matching` `portfolio-project`
