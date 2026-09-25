# Bridge X Brief — Project Continuity

**Purpose:** the durable, version-controlled home for this repo's current project state — active constraints, approved decisions, verified state, open items — plus links to supporting documents. This is a living document that changes in place as state evolves; it is not a spec and not a copy of any spec's content — read the linked documents for the actual substance.

Adopted per the stack-wide continuity pattern established in the Agent Attribution Engine's own continuity doc (`MoCrypto-OnChain/BX-Creative-Labs`, `docs/aae/PROJECT-CONTINUITY.md`) and this stack's root `CLAUDE.md` ("Canonical Spec Versioning & Placement Convention"): root-level pointer files (`CLAUDE.md`, `AGENTS.md`) hold pointers only, this file is the canonical landing point they resolve to.

**Cross-repo role (important):** this repo is a **public** repo and is the canonical source of the Bridge X Brief editorial content, published to `main` at a specific pinned validation commit used elsewhere in the stack. As of this PR, `MoCrypto-OnChain/BX-Creative-Labs`'s Vantage pipeline (see that stack's `dev/Vantage` docs) treats Edition 007 of this repo as its proof case, pinned at commit `7da964951c7110e613c37f9a6ef349bfe7af24a8`. **This repo's own continuity doc does not restate that pin as a fact** — the pin is Vantage's concern to track and re-verify, not this repo's; stating it twice would create exactly the kind of duplicated identifier this pattern exists to avoid. Anyone consuming this repo as a source-of-truth fixture should re-verify the actual commit/hash directly rather than trusting either doc's restatement.

## Governing reference

- **Master governing spec:** [`aae-spec-v8.md`](https://github.com/MoCrypto-OnChain/BX-Creative-Labs/blob/main/docs/specs/aae-spec-v8.md) (`MoCrypto-OnChain/BX-Creative-Labs`) — the one governing reference this repo aligns to as part of ecosystem-wide continuity-pattern adoption (ratified 2026-09-11, folding in the nine owner-level decisions as binding implementation authority). This repo has no product-specific spec of its own — it is an editorial-content repo, not a software product.
- **Existing repo documentation** (pre-existing, not yet reorganized into this pattern, linked as-is): [`README.md`](../../README.md) — states this is Bridge X Capital's evidence-backed publication on digital-asset policy, stablecoins, Web3 infrastructure, and institutional adoption; `editions/` holds the published editions and `recovery/` holds dated recovery briefs — read those directories directly for current contents rather than trusting a listing restated here (the previous listing in this bullet had gone stale by the time Editions 008 and 009 landed).

## Approved decisions

- This repo adopts the stack-wide continuity pattern (this file + pointer-only `CLAUDE.md`/`AGENTS.md` + CI gate) as part of ecosystem-wide alignment to `aae-spec-v8.md`, decided 2026-09-11 (see "Build sequencing" in BX-Creative-Labs's `docs/aae/PROJECT-CONTINUITY.md`).
- **Covers for Editions 001–004 approved by the owner, 2026-09-25**, after a correction pass replaced art that had shipped against the wrong edition subjects. Alt text for those covers is defined by the cover-correction manifest that accompanied the correction package, not written ad hoc on the pages.

## Verified state

- No continuity doc existed in this repo before this PR.
- `editions/` directory listing confirms Edition 007 (`007-the-token-sale-is-being-rewritten`) is the latest edition folder present at the time of this PR. Its content and any hash/commit claims made about it elsewhere were not re-verified as part of this PR.
- **Cover correction, 2026-09-25:** Editions 001–004 shipped with covers generated for the wrong edition subjects ([`bridge-x-brief#5`](https://github.com/MoCrypto-OnChain/bridge-x-brief/pull/5), mirrored in `Production-Site#79`). Corrected in [`bridge-x-brief#6`](https://github.com/MoCrypto-OnChain/bridge-x-brief/pull/6) and [`Production-Site#80`](https://github.com/MoCrypto-OnChain/Production-Site/pull/80) — check each PR's own state directly rather than trusting a status word here. Web and master files for all four were SHA-256-verified against the package manifest before being copied in; alt/`og:image:alt` were updated on the edition pages, archive and index; Edition 001's page, which previously had no cover figure or og/twitter tags, now has them. Editions 005–009 were not touched. Three of the four covers were re-assigned existing approved art; only 002's art is newly generated.
- This repo is public (unlike most repos in this rollout) — nothing added by this PR changes that, and nothing sensitive has been added here.

## Open items

- **Real-world-assets cover art has no home in this repo.** It was removed from Edition 003 in the cover correction; the manifest says to keep it in a covers archive for a future RWA edition, but no such archive exists in this repo (or in Production-Site). The file is now recoverable only from git history (the replaced cover-003 commit) or from wherever the owner keeps originals — confirm a copy exists, and decide where it lives, before the next RWA edition needs it.
- **Edition 002's new cover has incomplete provenance.** The manifest records its generator as Codex (image only) and the original filename/hash, but leaves `model` and `generatedAt` null. Backfill if a full provenance record matters.
- A full state audit (which editions are published live vs. staged, current relationship between `recovery/` briefs and published content) has not been done as part of this PR — scope here was structural adoption of the pattern, not a content audit.

## Handoff history

- 2026-09-11: continuity pattern adopted (this PR), aligning this repo to `aae-spec-v8.md` as the stack's governing reference per ecosystem-wide alignment.
- 2026-09-25: covers for Editions 001–004 corrected and approved by the owner (see "Verified state"). Related, separate from this repo: Production-Site's `BXB production smoke` workflow had been failing on a stale Edition 007 asset filename, unrelated to the covers; fix tracked in [`Production-Site#81`](https://github.com/MoCrypto-OnChain/Production-Site/pull/81) — check its state directly.

## How this file should be kept in sync

This file is the authoritative continuity record for this repo — `CLAUDE.md` and `AGENTS.md` defer to it, not carry their own status. Enforced by `.github/workflows/continuity-check.yml`: root pointer files must reference this file's path and must never restate a version-specific `aae-spec-vN.md` filename.
