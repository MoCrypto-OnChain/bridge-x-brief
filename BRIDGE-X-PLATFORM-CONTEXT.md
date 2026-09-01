# Bridge X Capital — Full Platform Context Briefing

Drop this in the repo root (or paste as the first message in a new Claude
Code session) so nothing has to be re-explained from scratch. This is the
full-platform version — broader than any single repo's own CLAUDE.md.

## The parent company and its subsidiaries

**Bridge X Capital.AI Corp** is the founder's parent company — Web3
consulting, crypto/financial education, training, product development, and
doctrine publication. Three standalone-but-related companies sit under it:

1. **Bridge X Capital / Bridge X Platform** — the core education/community
   product (Doctrine, Academy, BridgeBot, institutional portal)
2. **VeriBridge** — decentralized identity/asset verification, its own
   roadmap and token (VRB)
3. **BX Creative Labs** — builds LaunchPad AI (see below)

All three are designed and marketed as companies that can stand on their
own, even though there's real internal overlap and shared infrastructure.

## Stack, across the board

Next.js/TypeScript frontends, Supabase backend, Vercel deployment as the
default pattern. GitHub Pro, Stripe, Resend, Railway, and Cloudflare are
also in active use — **not yet fully reconciled** whether these run
alongside Vercel/Supabase or replace it for specific projects (e.g. BXB).
Ask rather than assume when a repo's actual stack isn't obvious from its
package.json.

## Design system (Bridge X Platform / VeriBridge)

Dark-first, premium, minimal, executive. Canonical color tokens (locked):
- Navy `#0b1b2b`, deep `#091523`, cyan/turquoise `#00d0c6`, gold `#f4b400`,
  muted `#7ea3ba`, card `#0f2236`, white `#ffffff`
- Font: Inter / -apple-system / Segoe UI
- Emerald family (`#16C871` / `#53FF9B`) reserved **only** for
  verification/success states (credentials, quiz pass, VeriBridge-verified)
- Gold = primary brand accent. Cyan = tech/BridgeBot moments. Emerald =
  verification/success only. Don't mix these roles.

Canonical logo: circular emblem, Manhattan-Bridge-style bridge motif,
Bitcoin "B" at center, gold ring border, dark charcoal/navy field, NYC
skyline detail, wordmark "BRIDGE X CAPITAL" below in gold.

## The 7 repos and what's in each

| Repo | What it is |
|---|---|
| **Production-Site** | Main Bridge X Platform app (public site, member portal, Doctrine reader, Academy shell, BridgeBot, admin). Currently has the wallet SDK / attribution history — see below. |
| **Academy** | Crypto Academy curriculum — 30 live modules out of a planned 100 (Tracks 01–03, 10 modules each). Learn-to-earn rewards flow in design: 4–5 completion checkpoints per module, BXC token payout. |
| **BridgeBot-Core** | BridgeBot AI assistant — long-term vision is for this to become the orchestrating "super agent" managing a team of other AI agents across the whole ecosystem, and to serve as the Academy's student-facing liaison. |
| **BX-Creative-Labs** | Houses LaunchPad AI (see below). |
| **veribridge-dao** | VeriBridge's DAO/governance layer. |
| **LaunchPad-Compiler** | LaunchPad AI's actual compiler codebase (see below) — Development branch has early v0.1/v0.2 work. |
| **bridge-x-brief** | BXB (Bridge X Briefings) editorial newsletter repo — lowest-stakes of the 7, no wallet/auth/payment surface. |

## Thread: BXC tokenomics (Bridge X Platform)

- Total/max supply: 500,000,000 BXC
- Allocation: 25% Community/Learn-to-Earn (125M), 20% Treasury/Reserve
  (100M), 20% Team & Founders (100M), 10% Ecosystem Development &
  Partnerships (50M), 20% Liquidity Provisioning (100M), 5% Marketing &
  Growth (25M). No advisor allocation.
- Reward loop: earn BXC via Academy learning activity → BXC becomes usable
  in the People Trust DeFi platform (staking, LP, yield). Earn-via-learning
  → use-in-DeFi is the intended flow, not two separate systems.

## Thread: VeriBridge

VeriBridge Master Blueprint ("Exodus Stack") covers: decentralized identity
(veriFI, DID wallet), financial/RWA credential verification, VeriWatch
monitoring, a Civic Integrity Network (election eligibility/custody/audit
proofs), post-quantum crypto resilience, governance, 7-stage enterprise
roadmap. VRB token max supply 1B. Founder's stated dilemma: doesn't want to
have to build out the full VeriBridge blueprint before Academy has real
modules students can work within — so treat VeriBridge as a longer-horizon
build, not a blocker for Academy/Platform Core progress.

Separately, there's a BridgeBot-powered MVP scaffold called **"Project
Scope Intelligence Portal"** — a construction/architecture scope-
verification tool (RAG chat over uploaded RFIs/meeting notes, WIC/NIC
classification, cited answers, shareable scope-verification reports).
Next.js/TypeScript/Supabase/pgvector/OpenAI stack. Its MVP 3.0 roadmap
phase ties back to VeriBridge provenance/cryptographic verification.

## Thread: BX Creative Labs / LaunchPad AI

LaunchPad AI is a "creative compiler" — turns a structured "Launch
Capsule" (brand rules, assets, scenes, timing, motion) into a native,
editable production project. DaVinci Resolve is the first production
target. Brand statement: "WE DON'T JUST DESIGN. WE LAUNCH." Tagline:
"BRANDS, BUILT TO LAUNCH."

**Protected architecture — do not merge/modify these three layers
casually:**
1. Frozen Compiler v0.3.1 (Windows portable)
2. Validated Resolve Adapter v0.4.2
3. Router v0.4.x (coordination/handoff layer only)

Canonical proof project: **LC-0001 "Project Helios"** (client: Helios
Dynamics, product: HELIOS ONE) — validated end-to-end with native Resolve
scenes, Fusion compositions, editable typography/motion, readback evidence.

Validation history: LC-TEST-001 through LC-TEST-004 passed. Next milestone
is **LC-TEST-005** — prove the same pipeline works on a second, different
brand capsule without adapter changes (proves generalization beyond
Helios).

Not yet built: finished LaunchPad.exe UX, capsule-builder interface,
drag-and-drop ingestion, multi-project management, non-Resolve adapters,
licensing/update system, cloud collaboration.

## Thread: BXB (Bridge X Briefings)

Editorial newsletter product. Design reference: Edition 007 mockup ("The
New Token Issuance Era") — Edition Card, Edition Detail article page,
Archive Grid of past editions, Social Media Assets (LinkedIn carousel, X
image). Goal is an agentic workflow that can take a mockup image and build
a matching site UI with working navigation/routing.

Separately (from an earlier chat session, not yet fully synced into the
repo): an HTML prototype (`bxb-prototype.html`) was built with real
cropped artwork substituted for placeholder gradients, plus a real
schema/validator pair —`edition.schema.json` (requires `hero`, `card`,
`socialSquare`, `socialLandscape`, `email` art keys per edition) and
`validate-editions.js` (fails build if required art is missing). Confirmed
working against two example editions (007, 006), both of which
deliberately fail validation since their social/email art doesn't exist
yet. **These files may not be in this repo yet — check, and ask the
founder to upload them if not.** No `.webp` conversion exists yet, only
007 and 006 have `edition.json` files at all.

## Thread: aXis Connect

Separate wallet project, own repo history (WO-0002 wallet balance display
feature). Stack: Next.js/TypeScript, Supabase auth/backend, **Alchemy
SDK** for RPC balance queries (Sepolia + Base Mainnet) — notably **not**
Dynamic Labs, unlike Production-Site's wallet code (see below). Feature
work follows a BridgeBot-orchestration process: Architect spec → Backend/
Frontend implementation → QA review, with Claude.ai drafting and a
separate Claude Code session doing live implementation.

**Standing long-term plan:** build a first-party wallet lane through aXis
Connect and only use a third-party dependency like Dynamic as needed,
rather than depending on Dynamic wholesale. This is scheduled, not
immediate — don't start it unprompted.

## Thread: the wallet SDK incident (Production-Site) — resolved, but know the history

A Dynamic Labs wallet SDK integration (email OTP, WAAS wallet creation,
password unlock/recovery, private-key export) appeared in Production-Site
via one large commit (`3fb80c46a`, "Establish autonomous current-source
candidate baseline") that the founder never personally instructed.

**This is fully resolved as of 2026-08-30:**
- Code-level security review: no high-confidence vulnerabilities. Wallet
  ops are fully delegated to Dynamic's SDK, private-key export gated
  behind password re-entry inside Dynamic's own isolated frame, nothing
  sensitive logged.
- Attribution: confirmed via a `CODEX_SANDBOX` reference in
  `vite.config.ts` that the commit came from Codex's own app-hosting
  scaffold, not a manual/malicious action — Codex had legitimate, granted
  repo access at the time.
- Two now-dead scaffold files from that same event
  (`app/chatgpt-auth.ts`, a "Sign in with ChatGPT" stub) were removed as
  unused dead code with a latent auth-bypass risk if ever wired up.
- `.openai/hosting.json` — initially assumed to be more of the same
  scaffold, but turned out to be **load-bearing**: `vite.config.ts`, the
  Sites build plugin, and the deploy artifact validator all depend on it
  for D1/R2 hosting bindings. It was renamed/relocated to
  `config/hosting.json` under first-party naming instead of deleted —
  **verify this landed and the build passes before assuming it's fully
  done** (was still an open PR as of this briefing).

**Standing practice going forward, for any repo:** treat any commit under
the founder's own git identity — human or agent — as unverified until
reviewed, especially ones using "autonomous," "recovery," or "baseline"
language in the commit message, since that's the exact vocabulary this
incident produced.

## Standing infrastructure rules (apply to all 7 repos)

- **Branch protection on `main`:** PR required before merge, zero required
  approvals (founder is sole owner, must never be blocked merging their
  own work), not enforced against admins (founder retains a manual
  bypass by deliberate choice).
- **Push policy for agents specifically:** Claude Code's own token
  authenticates as the founder's owner/admin identity and therefore
  *inherits* the bypass privilege — branch protection alone does not stop
  Claude Code from pushing straight to `main`. The actual guardrail is
  behavioral, stated in each repo's `CLAUDE.md`: **never push directly to
  `main`; always branch, commit, and open a PR; leave the merge decision
  to the founder.** The same policy is mirrored in `AGENTS.md` for Codex.
  Follow this in every repo even if a given repo's `CLAUDE.md`/`AGENTS.md`
  hasn't been created yet — treat the policy as platform-wide, not
  per-repo opt-in.
- **Codex code review:** enabled across all 7 repos — Auto review: Review
  my PRs, Trigger: On every push, Exhaustive: Enabled. Codex authenticates
  via its own separate GitHub App (not the founder's personal
  credentials) — its actual bypass status was never directly confirmed
  before Codex's reliability issues (see below) paused further live
  testing.
- **Claude Code's own GitHub token** is a fine-grained PAT scoped to all 7
  repos: Contents read/write, Pull requests read/write, Actions read-only,
  Workflows excluded entirely (no access). Stored as a global Windows
  User-level `GITHUB_TOKEN` environment variable, not a per-project
  `.env` file.

## Current tooling state (as of this briefing)

Codex/ChatGPT is being set aside for now due to severe, repeatedly-
reproduced reliability problems — not a one-off: confirmed against actual
usage data (85% of 5-hour limit remaining, 98% of weekly cap remaining, so
not a quota issue), tasks silently completing with no output rendered
until manually prompted again, and a broader documented pattern of Codex
slowdowns/stalls across the user base in 2026. **Claude Code is expected
to carry more of the day-to-day implementation load going forward.** For
a second-opinion/review pass on higher-stakes changes (auth, wallet,
deploy config), use Claude Code's own `/ultrareview` rather than relying
on Codex.

## Local dev environment

Repos are cloned under `C:\BX Ecosystem\dev\` on the founder's Windows
machine (confirmed path for Production-Site:
`C:\BX Ecosystem\dev\Production-Site`). Claude Code is invoked directly
via `claude` from inside each repo folder.
