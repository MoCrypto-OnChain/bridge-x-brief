# Bridge X Recovery Brief — August 9, 2026

## Purpose

This brief preserves the complete working state reached on August 9, 2026 across the Bridge X Brief publishing system and the Bridge X Capital Web3 Live enrollment, payment, onboarding, and launch operations.

No secret values are stored in this document or in source control.

## 1. Bridge X Brief publishing state

### Canonical product system

- Editions 001–004 remain the locked design and editorial reference.
- Each weekly issue produces two coordinated products:
  1. the complete sourced HTML brief published at `brief.bridgexcapital.ai`; and
  2. a native, editable PowerPoint carousel for LinkedIn.
- The carousel and HTML brief must share the same thesis, factual record, terminology, and primary-source ledger.
- The BXB visual system remains fixed: 16:9 landscape composition, deep navy field, restrained grid, green/gold/blue accents, BXB signature, edition number, one systems-level visual thesis, and bottom-anchored headline treatment.
- Future editions change the issue-specific content; they do not introduce a new visual language.

### Edition 005

- Title: **The CLARITY Act Reaches the Senate Floor.**
- Subtitle: **America's digital-asset rulebook is closer—but not complete.**
- Publication month: August 2026.
- Central distinction: Senate leadership filed cloture on the motion to proceed; the bill has not passed the Senate.
- Full article path: `editions/005-clarity-reaches-the-senate-floor/index.html`.
- Canonical cover: `assets/bridge-x-brief-cover-005.svg`.
- LinkedIn carousel: `social/Bridge_X_Brief_005_LinkedIn_Carousel.pptx`.
- LinkedIn caption: `social/LinkedIn_Post_005.md`.
- Homepage begins **August 2026 · Volume 02**, followed by preserved **July 2026 · Volume 01** editions.

### Edition 005 carousel sequence

1. Canonical cover: cloture filed → 60-vote Senate gate → final law not yet.
2. Procedural signal: House passage, cloture filing, next Senate gate.
3. Headline discipline: what moved and what did not.
4. Rulebook architecture: SEC, CFTC, platforms, custody, customer assets, conflicts, and decentralization.
5. Floor fight: compliant innovation and enforceable protection.
6. Main Street test: access, protection, and competition.
7. Direct reader destination to the full sourced brief.

### Primary sources retained

- U.S. Senate Daily Press floor record.
- Congress.gov H.R. 3633 record.
- Senate Banking Committee majority materials.
- Senate Banking Committee minority analysis and issue briefs.
- House Financial Services Committee passage record, bill text, and section-by-section summary.

## 2. Bridge X Capital Web3 Live operational state

### Production and launch

- Hosted project: `bridge-x-capital-overhaul`.
- Current production deployment succeeded at `https://bridge-x-capital-overhaul.attentivedetail.chatgpt.site`.
- Custom-domain cutover to GoDaddy remains a DNS operation; the application build is production-capable.
- Browser favicon and social-sharing metadata use the Bridge X Capital brand asset; the existing header logo was intentionally preserved.

### Enrollment data model

- Enrollment records are stored in the application D1 database table `web3_live_enrollments`.
- Payment state is stored in `web3_live_payments`.
- Stripe event idempotency is stored in `stripe_webhook_events`.
- Enrollment records include the selected pathway, plan, payment rail, interests, notes, marketing consent, versioned terms acceptance, versioned Community Guidelines acceptance, access status, onboarding email status, and timestamps.
- The admin enrollment dashboard joins enrollment and payment records, exposes payment/access/onboarding state, displays consent evidence, supports CSV export, and permits a manual welcome-email retry for paid records.

### Stripe integration

- Stripe Checkout is created server-side using `STRIPE_SECRET_KEY`.
- Stripe webhooks are verified using `STRIPE_WEBHOOK_SECRET`.
- The endpoint is `/api/stripe/webhook`.
- Checkout metadata includes the Bridge X enrollment reference so the webhook can reconcile the payment to the learner record.
- The live endpoint successfully returned HTTP 200 for `checkout.session.completed` and updated the associated payment record.
- A restricted $5 production-validation option was added for controlled live testing.
- Control variables retained by name only: `STRIPE_SECRET_KEY`, `STRIPE_WEBHOOK_SECRET`, `STRIPE_CHECKOUT_MODE`, and `STRIPE_TEST_EMAIL_ALLOWLIST`.
- The $5 production-validation route must remain restricted and must not be visible to ordinary public visitors.

### Community Guidelines and terms

- Enrollment requires versioned acceptance of the Web3 Live pre-enrollment terms.
- Enrollment separately requires versioned acceptance of the Bridge X Community Guidelines.
- The guidelines establish a professional, respectful, learning-centered cohort environment and distinguish the ecosystem from entertainment or social-media behavior.
- Current version date: `2026-08-09`.

### Welcome-email workflow

- Welcome delivery uses Resend through `RESEND_API_KEY`.
- Paid webhook events attempt automatic welcome delivery.
- Successful delivery sets onboarding status to `sent`, records the send timestamp, and activates access.
- Failed delivery remains visible in the admin dashboard and can be retried with **Send welcome**.
- The sender-domain verification for `bridgexcapital.ai` was pending DNS propagation during this working session; Resend must show the domain as verified before branded production delivery is considered complete.

### Important safety and continuity rules

- Never commit Stripe or Resend secret values.
- Do not treat a successful browser return as payment confirmation; webhook verification remains authoritative.
- Do not expose the $5 validation control publicly.
- Do not activate access from an unverified client request.
- Preserve enrollment, payment, consent, webhook-event, access, and email-delivery state as separate auditable fields.

## 3. Commit record preserved in the site repository

- `d58013a` — Prepare secure Web3 Live checkout handoff.
- `d717714` — Add signed Stripe payment webhook.
- `5acec8f` — Restrict Stripe sandbox checkout.
- `43f7b3e` — Fix Web3 Live enrollment checkout handoff.
- `daef8f9` — Add required Bridge X community guidelines.
- `b9cbfd4` — Add private five-dollar live validation checkout.
- `2d3a497` — Add branded favicon and social sharing metadata.
- `6f4fdca` — Add launch operations, onboarding, and audit controls.

## 4. Immediate continuation point

1. Confirm the Edition 005 GitHub Pages build and social image render.
2. Upload the PPTX carousel to LinkedIn as a document and use the preserved caption.
3. Confirm Resend domain status changes from pending to verified.
4. Run one controlled paid enrollment using an approved address and confirm: Stripe checkout → signed webhook → paid status → welcome email → active access.
5. Complete GoDaddy cutover only after the custom-domain DNS targets are verified.

## 5. Canonical weekly BXB workflow

1. Research only current, decision-relevant developments.
2. Preserve primary-source receipts before drafting.
3. Write the full HTML brief in the established BXB editorial structure.
4. Create the canonical 16:9 cover in the Editions 001–004 design system.
5. Derive the native PowerPoint carousel from the same article—never as an unrelated redesign.
6. Validate legibility, spacing, source notes, links, and visual continuity slide by slide.
7. Publish the issue, add the month grouping, and preserve the complete state with a recovery brief and Git commit.
