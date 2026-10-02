# Guided Setup and Continuity — Documentation Review

Date: 3 October 2026  
Baseline: `9771ad5cb9d68fb9044a5f4a650d89f7a1195786`

This records a static cross-document review and scenario walkthrough of the guided setup changes. It is validation evidence, not an additional runtime procedure.

No independent model sessions, live provider writes, or cross-provider behavior tests were executed. The expected transitions below were checked against the edited specification, setup workflow, runtime protocol, README, and launchers. They do not prove that every model will follow the instructions.

## Scenario walkthroughs

| Scenario | Required transition checked in the documents | Review |
| --- | --- | --- |
| Ready seed, persistent manual saving | Setup prepares environment → awaiting save → saver confirms → Ready; no narration | Consistent |
| Persistent direct writes | Establish actual capability → save environment → confirmed write result → Ready; no write merely to probe | Consistent |
| Explicit temporary play | Explicit choice and limitation → session agreement → separate activation; no durable files required | Consistent |
| Existing valid environment file | Validate current content and durable location → reuse without repeating resolved questions | Consistent |
| Existing durable equivalent | Identify and reuse complete equivalent → update only missing fields; no competing definition | Consistent |
| Agreement only in an old chat | Obtain the agreement → durably record it → save confirmation before persistent launch | Consistent |
| Simple new opening | First natural opening pause → prepare both state/history → save at first agreed checkpoint; no complexity threshold | Consistent |
| Stop before opening boundary | Prepare actual narrated situation/events → save at interruption checkpoint; invent no intervening events | Consistent |
| Manual checkpoint | Complete replacements by default → exact pack/run/destinations → pending until all saves confirmed | Consistent |
| Partial or failed save | State succeeds, history fails → checkpoint remains pending → pause developments → retry/fallback | Consistent |
| Resume in a new chat | Resolve pending updates → load current environment and selected run records → reconstruct → continue | Consistent |
| Replay same seed | New run identity → shared seed only → separate state/history and destinations | Consistent |
| Provider change | Save pending updates → same authority and run → validate new access → save configuration changes | Consistent |
| Missing/conflicting continuity | Obtain relevant authoritative records or explicitly resolve conflict; never invent recovery | Consistent |
| Hidden narrator material | Agreed private handling → listener-visible exports exclude hidden truth; labels provide no access control | Consistent |
| Temporary-to-persistent conversion | Establish authority → save environment and recoverable continuity → disclose gaps → continue persistently | Consistent |

## Representative status walkthroughs

These are illustrative traces, not outputs from executed model tests:

- Manual setup: **Setup incomplete** → agreement and complete environment record prepared → **Agreement complete — awaiting save** → designated saver confirms → **Story Environment: Ready** → setup stops.
- Partial continuity save: both intended records prepared → state write succeeds, history write fails → **Continuity update pending** → no further developments → history retry succeeds and pair is consistent → **Continuity saved**.
- Temporary launch: explicit temporary session agreement → ready without durable save → separate runtime activation → narration; persistent record initialization remains inapplicable until deliberate conversion.

## Mechanical checks and limits

Mechanical checks passed: whitespace/diff checks, balanced code fences in all Markdown files, 26 relative Markdown link targets, and a search for superseded optional-environment and subjective core-record creation instructions. Private story packs, the public example seed, and creative worldbuilding content are outside this change.

Prompt instructions cannot guarantee enforcement across providers. A later runtime trial should supply the edited sources and record actual setup, first checkpoint, manual-save confirmation, and resume outputs. Live-write validation must exercise real permissions and results in the chosen environment; this review makes no capability claim for ChatGPT Projects or Google Drive.
