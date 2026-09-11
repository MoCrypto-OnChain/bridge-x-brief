# Bridge X Brief — Project Continuity

**Purpose:** the durable, version-controlled home for this repo's current project state — active constraints, approved decisions, verified state, open items — plus links to supporting documents. This is a living document that changes in place as state evolves; it is not a spec and not a copy of any spec's content — read the linked documents for the actual substance.

Adopted per the stack-wide continuity pattern established in the Agent Attribution Engine's own continuity doc (`MoCrypto-OnChain/BX-Creative-Labs`, `docs/aae/PROJECT-CONTINUITY.md`) and this stack's root `CLAUDE.md` ("Canonical Spec Versioning & Placement Convention"): root-level pointer files (`CLAUDE.md`, `AGENTS.md`) hold pointers only, this file is the canonical landing point they resolve to.

**Cross-repo role (important):** this repo is a **public** repo and is the canonical source of the Bridge X Brief editorial content, published to `main` at a specific pinned validation commit used elsewhere in the stack. As of this PR, `MoCrypto-OnChain/BX-Creative-Labs`'s Vantage pipeline (see that stack's `dev/Vantage` docs) treats Edition 007 of this repo as its proof case, pinned at commit `7da964951c7110e613c37f9a6ef349bfe7af24a8`. **This repo's own continuity doc does not restate that pin as a fact** — the pin is Vantage's concern to track and re-verify, not this repo's; stating it twice would create exactly the kind of duplicated identifier this pattern exists to avoid. Anyone consuming this repo as a source-of-truth fixture should re-verify the actual commit/hash directly rather than trusting either doc's restatement.

## Governing reference

- **Master governing spec:** [`aae-spec-v8.md`](https://github.com/MoCrypto-OnChain/BX-Creative-Labs/blob/main/docs/specs/aae-spec-v8.md) (`MoCrypto-OnChain/BX-Creative-Labs`) — the one governing reference this repo aligns to as part of ecosystem-wide continuity-pattern adoption (ratified 2026-09-11, folding in the nine owner-level decisions as binding implementation authority). This repo has no product-specific spec of its own — it is an editorial-content repo, not a software product.
- **Existing repo documentation** (pre-existing, not yet reorganized into this pattern, linked as-is): [`README.md`](../../README.md) — states this is Bridge X Capital's evidence-backed publication on digital-asset policy, stablecoins, Web3 infrastructure, and institutional adoption; `editions/` currently runs through `007-the-token-sale-is-being-rewritten`; `recovery/` holds dated recovery briefs, most recently `BXB_007_2026-08-24.md`.

## Approved decisions

- This repo adopts the stack-wide continuity pattern (this file + pointer-only `CLAUDE.md`/`AGENTS.md` + CI gate) as part of ecosystem-wide alignment to `aae-spec-v8.md`, decided 2026-09-11 (see "Build sequencing" in BX-Creative-Labs's `docs/aae/PROJECT-CONTINUITY.md`).

## Verified state

- No continuity doc existed in this repo before this PR.
- `editions/` directory listing confirms Edition 007 (`007-the-token-sale-is-being-rewritten`) is the latest edition folder present at the time of this PR. Its content and any hash/commit claims made about it elsewhere were not re-verified as part of this PR.
- This repo is public (unlike most repos in this rollout) — nothing added by this PR changes that, and nothing sensitive has been added here.

## Open items

- A full state audit (which editions are published live vs. staged, current relationship between `recovery/` briefs and published content) has not been done as part of this PR — scope here was structural adoption of the pattern, not a content audit.

## Handoff history

- 2026-09-11: continuity pattern adopted (this PR), aligning this repo to `aae-spec-v8.md` as the stack's governing reference per ecosystem-wide alignment.

## How this file should be kept in sync

This file is the authoritative continuity record for this repo — `CLAUDE.md` and `AGENTS.md` defer to it, not carry their own status. Enforced by `.github/workflows/continuity-check.yml`: root pointer files must reference this file's path and must never restate a version-specific `aae-spec-vN.md` filename.
