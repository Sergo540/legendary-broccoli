# Copilot coding agent instructions for legendary-broccoli

This repository contains minimal content. These instructions tell the Copilot coding agent how to safely and usefully make changes when asked to "Onboard this repo" or to continue work automatically.

Purpose
- Help contributors and the automated Copilot coding agent make focused, high-quality changes.
- Preserve human intent: prefer small, well-tested edits and open PRs for larger changes.

Scope / what the agent may change
- Small fixes, documentation, tests, tooling, and CI that are low-risk and follow repository conventions.
- Add new files necessary to satisfy a user's request (examples, docs, scripts).

Do NOT change without explicit human approval
- Broad architectural rewrites or refactors.
- Secrets, keys, tokens, CI secrets, or anything under `.github/workflows/` that modifies production deployment flows.
- Changes that add or update external credentials, Docker images, or infrastructure-as-code without an explicit human step.

Repository-specific notes
- This repo currently only contains a `README.md` and a `LICENSE` file. There is no test suite or build system detected. Prefer conservative edits.
- If adding code, include a minimal test harness and update the README with run steps.

How to run checks (agent should run when possible)
1. Look for language-specific manifests (`package.json`, `pyproject.toml`, `requirements.txt`, `go.mod`, etc.).
2. If present, run the project's test command. If no manifest is found, only run simple lint/syntax checks for added files.

Pull request and commit style
- Small, single-purpose commits with clear messages.
- Open a PR for anything more than a trivial one-file change.
- Include a short PR description explaining the change and verification steps.

Human contacts / reviewers
- If unsure, open a draft PR and request review from the repository owner or contributors.

Additional guidance for the agent
- Use the repository's preferred language/tools when known.
- Run quick verification (unit tests, typecheck, lint) after edits. Report PASS/FAIL.
- When making edits, add or update docs illustrating how to run or test the change.

FAQ
- Q: Can the agent add CI workflows? A: No — changing CI or deployment files requires a human reviewer.
- Q: Can the agent commit directly to `main`? A: Avoid direct commits to the default branch for non-trivial changes. Use a feature branch and open a PR.

Last updated: 2025-10-19
