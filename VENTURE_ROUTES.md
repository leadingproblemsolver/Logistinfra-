# VENTURE ROUTES

Venture-specific routing only. Gate definitions (−1, 0, 1, 2), priority classes and the output card live in CONTROLLER.md and are not repeated here. This file says what counts as evidence at each gate, when a call is justified, and when to kill.

Everything named below is REPORTED, not VERIFIED, until STATE_LEDGER.md holds a dated evidence reference. Named systems are routing destinations, not proof they currently work.

## Selecting a route
1. Identify the actor whose decision unlocks the target (employer, buyer, customer, maintainer, evaluator).
2. Use the venture whose actor that is. Hybrid: use the one whose gate is nearest; hand the other its output.
3. Reuse the existing pipeline named in the route. Do not add a parallel one.
4. A gate counts as passed only with a ledger-cited reference and date.

## Call decision (all ventures)
Book a call only if the answer to at least one is yes, and no cheaper action gives equal information:
- Does it unlock access to a decision-maker I cannot otherwise reach?
- Is the workflow or purchasing context unclear enough that the offer cannot be written without it?
- Is a spoken commitment (scope, pilot, price) the next required step?

Otherwise send the offer, demo, listing, checkout link, PR or application.

## Physical ecommerce (Zynro: Amazon US, CJ Dropshipping/Alibaba sourcing)
Existing pipeline, REPORTED: Zynro Supplier Router → product validation → Amazon/CJ listing → creative → sales receipts.
- −1 evidence: observable marketplace demand and competitor sales, landed cost and fees giving a unit-economics figure, supplier feasibility (stock, shipping time, restrictions, category gating).
- 0 evidence: one compliant listing copied from an existing listing template, exact SKU-to-supplier mapping, real product media.
- 1 evidence: listing matches the product received or specified, checkout works, order path to supplier fulfilled or fully simulated with the supplier's confirmation, shipping time within what the listing promises, returns path known.
- 2 evidence: attributed paid orders, contribution margin after fees, ads and returns, and an acquisition source that repeats.
- Calls: none with consumers. Supplier contact only for samples, MOQ or shipping terms.
- Kill: contribution margin at a realistic price is zero or negative, or supplier cannot meet the listing's promise.
- Do not scale ads before one verified end-to-end order.

## Digital products
Existing assets, REPORTED: automation and reliability-related assets. Commercial validation and full packaging are incomplete unless the ledger shows otherwise.
- −1 evidence: a named operator with a recurring problem who tries it, replies with specifics, or pays.
- 0 evidence: an existing asset packaged into one bounded deliverable with install, use and evaluate instructions.
- 1 evidence: an independent user installs from scratch and gets the promised result; payment path and file delivery tested.
- 2 evidence: a paying customer with successful use; note support burden and refunds.
- Calls: only if the buyer's workflow needs diagnosis. Otherwise demo or checkout link.
- Kill: no operator will use it free after direct exposure.
- Do not add features before demand is tested.

## B2B services and sales
Existing pipeline, REPORTED: Market Router, Direct Human Gap Router, Clay/Apollo workflows, existing prospect conversations and outreach. Warm existing conversations come before new outbound.
- −1 evidence: a named team with an observable workflow gap, an identified owner, a business consequence drawn from evidence.
- 0 evidence: an existing diagnostic, Loom or sample reworked for that team.
- 1 evidence: the bounded problem is solved on their real or representative input, and delivery is verified.
- 2 evidence: paid pilot, measured improvement, repeat work or a referral.
- Calls: if the gap and offer are clear, go straight to a paid-pilot or commitment message. If workflow or buyer context is unclear, use one diagnostic call.
- Never invent a company's losses, tools or metrics.
- Kill: owner confirmed no problem, or no reply after the planned touch sequence.

## Software, GitHub, OSS
Existing assets, REPORTED: GitHub account `leadingproblemsolver`, including `Followup-Flow`. Other repository state must be inspected, not assumed.
- −1 evidence: a real failing behavior, issue, or maintainer requirement, with a link.
- 0 evidence: reproduction plus a minimal working baseline.
- 1 evidence: fix or feature with tests, a hostile or negative case, invariants and side-effect order checked, and you can rebuild it unaided.
- 2 evidence: merged PR, maintainer review, deployed use by others, or a paid implementation.
- Calls: none. Use the issue thread or PR.
- Prefer existing repos, open issues and partial work. No showcase repos built only to add artifacts.

## Career (employment, internships, competitions)
Existing assets, REPORTED: technical proof, internships, applications, OSS contributions, Devpost.
- −1 evidence: the opportunity is live, you meet eligibility, the deadline and the evaluator's requirements are confirmed from the source.
- 0 evidence: the closest existing proof, with the smallest gap repaired and mapped to the stated requirements.
- 1 evidence: a defensible artifact, demo or contribution whose behavior an evaluator can verify.
- 2 evidence: an employer or judge acted: assessment, interview, accepted contribution, competition result, offer.
- Calls: a warm introduction to an evaluator, or scheduled screens. Do not request calls to create activity.
- Certifications only when they change eligibility or evaluator confidence.
- Submission is exposure, not Phase 2.
- Kill: ineligible, or the deadline has passed.

## Hybrid
Name the unlocking actor. Run that venture's route. Hand outputs to the other as evidence, not as parallel work.
