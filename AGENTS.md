## bridge-x-brief — Repo Context & Rules

**Purpose:** Bridge X Briefings (BXB) editorial newsletter — public-facing intelligence publication for Bridge X Capital. Lowest-stakes repo in the stack: no wallet, auth, or payment surface.

**Push policy:** No direct pushes to `main`. Always branch + PR. Owner makes the merge decision.

**Agent diagnostic caution:** Before stating a root cause for a CI/deploy/access failure, verify it against actual evidence — logs, curl output, git history — rather than asserting the most plausible-sounding explanation. If you can't get direct evidence, say so explicitly rather than presenting a guess as a finding.

**Cross-repo context:** This repo is part of the wider Bridge X Capital stack — see `BRIDGE-X-PLATFORM-CONTEXT.md` in the **Production-Site** repo root for full platform context, design system, and prior incident history across other repos. Deliberately **not** copied into this repo: this repo is a GitHub Pages site published directly from `main` at path `/` (legacy build, `.nojekyll`, no build step of any kind), so any file placed at its root becomes publicly fetchable exactly like every other page on the live site. That file contains non-public operational details (git-bypass model, PAT storage/scope, incident history, unreleased plans) and must not be added here.

**Status:** Clean as of 2026-08-31 — last deploy (GitHub Pages) succeeded, no open PRs, nothing pending. Note: `Production-Site` also contains a separate, more actively developed BXB pipeline (`app/brief/`, `public/brief/`) that publishes the same editions independently. The relationship between that pipeline and this repo's own content has not been reconciled — check before assuming either one is the canonical source for a given edition.
