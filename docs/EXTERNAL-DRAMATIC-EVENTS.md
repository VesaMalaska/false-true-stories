# False True Stories — External Dramatic Events Contract

## Purpose and scope

Describe how an optional, independent dramatic-event producer such as SpinnyWheel can influence an FST Story Run without taking over the narrator, overriding the listener, or becoming an alternative source of fictional truth.

This document is an **FST-facing integration contract**, not the SpinnyWheel algorithm, API specification, or implementation. It does not require SpinnyWheel, numerical RPG attributes, dice-based action resolution, a Svelte application, or automatic event generation. An FST run must remain playable without an event producer.

## Responsibility boundaries

| Responsibility | Owner |
| --- | --- |
| Define fictional starting truth and boundaries | World Seed and FST Story Pack |
| Maintain established run truth and character knowledge | FST Story Runtime |
| Choose a trigger/pressure policy, track its own operational state, and propose an event outcome | External event producer (when enabled) |
| Interpret an accepted event within fictional causes, NPC motivations, tone, and knowledge boundaries | FST narrator |
| Decide the protagonist's voluntary actions in player/director modes | Listener |
| Persist actual consequential developments, revelations, and state changes | FST Story Runtime |

An external result is a **proposal for dramatic development**, not automatically canon. Only a resulting fictional event that has been validly established within the Story Run becomes run truth.

## Optional event cycle

When an enabled integration calls for an event:

1. **Trigger:** The producer's documented policy determines whether to generate an outcome. The FST narrator MUST NOT silently force extra rolls merely to manufacture drama. Trigger policies, pressure progression, and the producer's probabilities are the producer's responsibility, not FST's.
2. **Context:** FST supplies only the context needed for the event: relevant situation, permissible creative space, current pressures, tone, protected boundaries, and any information the producer is explicitly allowed to use. Distinguish established truth from inference.
3. **Propose:** The producer returns an outcome category and any optional guidance. FST MUST NOT presume a universal list of categories or a mandatory numeric representation.
4. **Check:** Before establishing a fictional consequence, the narrator/runtime checks the proposed development against world canon, current state, character knowledge, protected mysteries, causality, listener boundaries, and the current interaction profile.
5. **Interpret:** The narrator expresses a compatible outcome through existing factions, NPC agency, circumstances, and established possibilities. A category alone does not dictate a specific plot event.
6. **Preserve:** Once a consequential development becomes true, FST records its fictional effect and the relevant state/history change at the normal checkpoint. Operational producer state needed for reproducible continuation is maintained separately from fictional canon.

The producer MAY return a neutral or continuation outcome that creates no new fictional event. Do not force a twist when no development is warranted.

## Incompatible outcomes

If a proposal conflicts with an established truth or protected boundary, the narrator MUST NOT rewrite that truth to accommodate it.

A compatible interpretation within the *same outcome intent* is preferred when possible. If no faithful interpretation exists, the integration MUST follow an explicitly defined non-destructive fallback (for example: no fictional change and an event-resolution failure recorded operationally, or a producer-specified safe retry policy). FST MUST NOT secretly invent a second producer roll or silently change the event category. The integration's chosen fallback policy should be documented before live use.

An event cannot be used to retroactively decide that evidence was false solely to generate surprise. Later revelations may change a character's interpretation only when consistent with what was established.

## Player agency and action resolution

External dramatic events never decide the listener's voluntary protagonist actions, speech, intentions, or choices in `player` and `director` interaction modes. They may change the world around the protagonist, with the narrator stopping at meaningful player decision boundaries.

An event producer is **not** automatically an action-resolution system. A listener's attempt to pick a lock, persuade a witness, or dodge a bullet follows FST's existing plausible-outcome rules unless a distinct, explicitly agreed mechanism is introduced. Do not roll for every action merely because a dramatic-event producer exists.

`story` and `balanced` modes retain their documented narrator initiative; enabling an event producer does not alter the selected profile, pacing, or detail.

## Off-screen events and knowledge protection

A producer may contribute to an event occurring outside the protagonist's presence when the event fits established world causality.

Separate:

- **Occurred:** What actually changes in the world and when.
- **Known:** Which characters could plausibly know or believe it, and how.
- **Revealed:** What the listener is shown in narration.

An off-screen event does not automatically become protagonist knowledge or listener-visible narration. Private narrator-only material and any event-planning context remain subject to existing FST private-material handling.

## Continuity and recovery

- Save the **fictional consequence** in the selected run's state/history when it matters; do not merely save the abstract roll category in place of the resulting event.
- Preserve enough **operational event state** to avoid losing pressure/trigger progression across checkpoints or provider changes if the selected producer requires it. It must remain identified with the same Story Pack and run and must not be mistaken for fictional canon.
- A transient/runtime-packet copy is not authoritative. Rebuild it from authoritative records and the producer's durable operational state where available.
- Avoid applying the same event twice during retries, interrupted saves, or resumed sessions. The integration needs a way to recognize previously applied outcomes, but this contract does not prescribe an event-ID format or storage schema.
- Do not expose narrator-only mysteries through listener-visible logs, exports, or settings.
- Failure or absence of an optional producer must not corrupt FST continuity. A run may continue with ordinary FST narration using its recorded state; any producer-specific pressure recovery must be handled explicitly before producer use resumes.

## Example: Wookland Shadows

A valid dramatic outcome during the hotel's aftermath could be a rival syndicate accelerating an existing plan, escalating pressure on corrupt officials. FST may establish that as an off-screen event, preserve the change, and reveal it later through an appropriate witness, newspaper, or intercepted message.

It must **not** decide Wez's response, reveal secret faction plans directly to Wez without a source, or change the protected explanation of the murdered politician solely to fit the dramatic category.

## Integration readiness checklist

Before enabling an external producer for a persistent run:

- [ ] Its trigger/pressure policy and outcome semantics are documented.
- [ ] Its operational state and selected run identity can be recovered after interruption.
- [ ] The event-to-narrative interpretation and conflict fallback policy are agreed.
- [ ] Fictional effects are saved via existing FST state/history checkpoints.
- [ ] Hidden knowledge and listener agency are protected.
- [ ] Duplicate application and provider handoff are addressed.
- [ ] The integration can be disabled without invalidating already established fictional truth.

## Guiding principle

> The event producer proposes dramatic pressure. The FST world determines what is possible. The narrator makes it fiction. The listener keeps the protagonist's agency.
