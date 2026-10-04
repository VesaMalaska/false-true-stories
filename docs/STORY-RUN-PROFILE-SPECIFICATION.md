# False True Stories — Story Run Profile Specification

## Purpose

Define the small set of explicit experience controls that govern how a False True Stories run feels during live narration.

A Story Run Profile is operational configuration, not fictional canon. It must be deterministic enough that different capable runtimes can interpret the same profile consistently, while remaining simple enough that a listener never needs to understand configuration syntax.

The profile exists to protect user experience from ad-hoc narrator improvisation.

## UX-first rule

> User experience is the primary design constraint of False True Stories. Framework rigor exists to make the experience reliable, not to expose complexity to the user.

The runtime MUST use documented defaults for optional settings that the user has not specified. Missing optional preferences MUST NOT block setup or storytelling.

A user may configure the experience conversationally. The runtime translates ordinary language into the defined profile semantics.

## Profile dimensions

The initial profile contains three independent dimensions.

### Interaction

Interaction controls how often the narrator deliberately yields protagonist agency to the listener.

Valid values:

- **story** — narrator normally carries events forward. Explicit hand-offs are reserved mainly for major character-defining or direction-changing moments.
- **balanced** — narrator maintains momentum while yielding at meaningful decisions often enough for the listener to shape the run. This is the default.
- **player** — narrator yields protagonist actions, dialogue, investigation, tactics, and other meaningful agency frequently.
- **director** — the listener may actively direct protagonist behavior and broader scene direction, approaching collaborative role-play or storytelling.

Higher interaction does not authorize trivial interruptions or constant menu prompts.

### Pacing

Pacing controls how quickly narrative time and story beats advance.

Valid values:

- **leisurely** — allows more pauses, intermediate beats, and room for scenes to unfold gradually.
- **cinematic** — moves decisively between meaningful beats while retaining atmosphere and character moments. This is the default.
- **rapid** — compresses transitions and low-value intermediate beats so the story advances quickly.

Pacing does not determine how much protagonist control the listener has.

### Detail

Detail controls descriptive density.

Valid values:

- **lean** — concise description focused on action, dialogue, and essential context.
- **rich** — substantial atmosphere, characterization, and sensory detail without unnecessary expansion. This is the default.
- **immersive** — deliberately fuller description and scene texture when compatible with pacing.

Detail does not determine pacing or interaction frequency.

## Default profile

Unless the user has expressed a different preference, use:

```text
interaction: balanced
pacing: cinematic
detail: rich
handoff_style: open
protagonist_override: always
```

These defaults are framework-defined. A runtime MUST NOT invent different defaults merely because another choice seems preferable.

## Open hand-offs

When the runtime yields agency, the normal hand-off style is open.

Prefer:

> Keller watches Maximilian carefully and waits. What does Max do?

Do not default to:

> A. Bluff  
> B. Leave  
> C. Confess

Finite options are appropriate when:

- the user asks for suggestions;
- the available choices are genuinely finite in-world;
- the user appears stuck and suggestions would help;
- accessibility or convenience clearly benefits from a short option list.

Even then, another plausible action remains allowed unless established story constraints prevent it.

## Protagonist ownership

The interaction level controls normal narrator initiative. It never removes the listener's ability to take control.

An explicit user statement about what the protagonist says, does, attempts, intends, or refuses is authoritative user intent for that moment unless it conflicts with an established boundary or physical impossibility.

The runtime MUST yield immediately and continue from that intent.

Example:

> Max stays relaxed, sits back down, and tells Keller plainly that he never signed the release.

The narrator must not replace that action with a different preferred response.

## Runtime changes

The profile may change during an active run through natural conversation.

Distinguish three cases.

### Persistent run-profile change

Examples:

- “From now on, let me make more of Max's decisions.”
- “Keep the descriptions shorter for the rest of this story.”

Update the run profile and preserve the change with the run's operational configuration at the next appropriate checkpoint.

### Temporary mode change

Examples:

- “Take over for a while; I just want to listen.”
- “For this investigation scene, ask me what Max does more often.”

Apply the temporary preference for the requested scope. Return to the stored baseline naturally when that scope ends.

### One-turn control grab

The user simply states an action, line of dialogue, or immediate intention.

Apply it without changing the stored profile.

Do not ask the user to classify the kind of change when ordinary language makes the intended scope clear.

## Conversational configuration

Users do not need to know the profile names.

Interpret natural requests according to the closest defined semantics.

Examples:

| User request | Interpretation |
| --- | --- |
| “Just tell me the story mostly.” | interaction: story |
| “A balanced amount of decisions is good.” | interaction: balanced |
| “Ask me what I want Max to do more often.” | interaction: player |
| “Let me direct this pretty closely.” | interaction: director |
| “Move things along faster.” | pacing: rapid |
| “Take your time with scenes.” | pacing: leisurely |
| “Keep descriptions tighter.” | detail: lean |
| “Make it really atmospheric.” | detail: immersive |

If the user's wording is ambiguous but the existing profile remains workable, keep the current value rather than interrupting the story for configuration.

## Setup behavior

Story Environment Setup MAY offer profile customization briefly when it is natural, but MUST NOT require the user to configure optional dimensions.

A suitable explanation is:

> I’ll use the standard balanced storytelling style unless you want the story to be more hands-off, more player-controlled, faster, slower, leaner, or more descriptive. You can change this at any time.

If the user gives no preference, apply the default profile and continue setup.

The profile must be associated with the selected run or clearly defined as the default for a newly created run. In an environment serving multiple runs, do not silently apply one run's changed profile to another run.

## Persistence

The profile is operational configuration rather than story truth.

Persist the selected run's baseline profile in the environment record or another clearly identified operational record. A storage system may represent it differently, but it must remain distinguishable from fictional canon.

Temporary mode changes and one-turn control grabs do not require persistence unless the user explicitly makes them permanent.

When a persistent profile change occurs during play, it may be batched with the next natural checkpoint. The story need not stop immediately merely to save a harmless experience-setting change.

## Portability

The semantics in this specification are provider-neutral.

A runtime may use different internal representations, but it must preserve:

- the defined dimensions;
- the defined defaults;
- open hand-offs as the normal style;
- explicit user protagonist override;
- conversational changes;
- separation of persistent, temporary, and one-turn changes.

## Guiding principle

> The framework defines the experience controls. The listener chooses preferences in ordinary language. The narrator executes them consistently.
