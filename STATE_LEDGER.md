# STATE LEDGER

A portable record of where state lives and what evidence exists. It holds pointers and last-verification dates, not copies of projects. It is not live state: nothing here updates itself. The controller proposes edits; the user (or an enabled Action) applies them.

## Rules
- One entry per source of truth. Pointer, not content.
- Never store credentials, customer data or private conversation text.
- `tag` uses CONTROLLER.md §1: VERIFIED, REPORTED, INFERRED, UNKNOWN.
- `gate` is the highest gate with a cited `evidence_ref`. No reference means the gate is not passed.
- A VERIFIED entry older than `stale_after` days counts as REPORTED until re-checked.
- If the source is unreachable, set `tag: UNKNOWN` and fill `missing_ref` with exactly what is needed (URL, chat title, export, screenshot).
- Keep `next_action` to one line with one external recipient.

## What the controller can and cannot read
| Source | Reachable? |
|---|---|
| This file, CONTROLLER.md, VENTURE_ROUTES.md | Yes, if uploaded to Knowledge. A static copy, not synced. |
| Text, screenshots, exports pasted into chat | Yes |
| Other ChatGPT conversations | No, unless pasted or exported |
| GitHub repos, Gmail, CRM, marketplace accounts | Only through an enabled Action/connector. Otherwise paste or screenshot. |
| Anything not listed | Treat as UNKNOWN |

## Entry template
```
id:
venture:        ecommerce | digital | b2b | software | career
source:         <URL / chat title / repo / tool>
access:         direct | connector | paste | none
claim:          <one line>
tag:            VERIFIED | REPORTED | INFERRED | UNKNOWN
gate:           none | -1 | 0 | 1 | 2
evidence_ref:   <URL / file / log / receipt, or none>
last_verified:  YYYY-MM-DD | never
stale_after:    <days>
missing_ref:    <what is needed, or none>
next_action:    <one action>  -> <external recipient>
```

## Entries
Initial values come from the owner's report on 2026-10-14. Nothing below except L1 has been inspected.

```
id: L1
venture: n/a
source: github.com/leadingproblemsolver/Logistinfra- (this repo)
access: direct
claim: Orchestration destination for portable Production OS config. Held no commits before this change. Not the source of truth for any venture.
tag: VERIFIED
gate: n/a
evidence_ref: git inspection, 2026-10-14 (no commits, no files)
last_verified: 2026-10-14
stale_after: 30
missing_ref: none
next_action: Upload the three files to the GPT Knowledge -> owner
```

```
id: Z1
venture: ecommerce
source: Zynro (Amazon US seller account, CJ Dropshipping/Alibaba sourcing, supplier router)
access: none
claim: Amazon US marketplace with CJ/Alibaba sourcing, product validation, fulfillment and unit economics work exists.
tag: REPORTED
gate: none
evidence_ref: none
last_verified: never
stale_after: 14
missing_ref: seller account status; listing URLs or ASINs; supplier SKU map; order history; Zynro Supplier Router location
next_action: Supply the live listing URL or order export -> controller
```

```
id: D1
venture: digital
source: automation and reliability-related assets (location not recorded)
access: none
claim: Assets exist. Commercial validation and full packaging are incomplete.
tag: REPORTED
gate: none
evidence_ref: none
last_verified: never
stale_after: 14
missing_ref: asset locations; any listing, price or sales record
next_action: Name the asset closest to packageable -> controller
```

```
id: B1
venture: b2b
source: Market Router; Direct Human Gap Router; Clay/Apollo workflows; prospect conversations (Gmail and CRM)
access: none
claim: Routers, workflows and warm prospect conversations exist.
tag: REPORTED
gate: none
evidence_ref: none
last_verified: never
stale_after: 7
missing_ref: warm conversations with a pending reply; router locations; CRM or export
next_action: Paste or list the warmest open conversation -> controller
```

```
id: S1
venture: software
source: github.com/leadingproblemsolver/Followup-Flow (URL derived from handle and repo name; not fetched)
access: none
claim: Repository exists under the leadingproblemsolver account.
tag: REPORTED
gate: none
evidence_ref: none
last_verified: never
stale_after: 14
missing_ref: README, test status, open issues, last commit date
next_action: Inspect the repo with a GitHub-enabled session -> controller
```

```
id: S2
venture: software
source: github.com/leadingproblemsolver (all other repositories) and OSS contributions
access: none
claim: Additional repositories and OSS contributions exist; state unknown.
tag: UNKNOWN
gate: none
evidence_ref: none
last_verified: never
stale_after: 14
missing_ref: repo list; PR and issue links
next_action: Inspect the account's repos and open PRs -> controller
```

```
id: C1
venture: career
source: applications, internships, Devpost entries, OSS contributions, employer correspondence
access: none
claim: Technical proof and applications exist; deadlines and evaluation status unknown.
tag: REPORTED
gate: none
evidence_ref: none
last_verified: never
stale_after: 7
missing_ref: open opportunities with deadlines; application status; any employer replies
next_action: List open opportunities with deadlines -> controller
```

## Active queue
Order is decided by CONTROLLER.md §2, not here. Keep at most three.
1. Identify the earliest-deadline qualified opportunity (C1) and run its route.
2. Surface the warmest unanswered commercial conversation (B1).
3. Inspect `Followup-Flow` (S1) if it maps to an opportunity from 1 or 2.
