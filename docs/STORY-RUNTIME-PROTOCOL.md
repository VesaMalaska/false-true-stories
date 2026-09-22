# False True Stories — Story Runtime Protocol

This protocol defines how a language model begins, continues, and preserves a False True Stories Story Run.

It governs runtime behavior after a playable World Seed exists. It does not define how to create a World Seed or require any particular language model, storage provider, application, or rigid file layout.

## Purpose

The story runtime turns a Story Pack into a continuous, responsive story while protecting the truth that the world and its current run have already established.

The runtime must:

- tell a compelling story first;
- preserve continuity;
- keep world truth separate from character and listener knowledge;
- allow characters and off-screen events to develop independently;
- offer listener choices only at meaningful moments;
- apply consequences honestly;
- record important new truths so the run can continue later.

> Story first. Machinery underneath.

## Required inputs

Before beginning or resuming a run, the runtime must read the available authoritative materials for that Story Pack.

These normally include:

- the False True Stories `README.md`;
- `docs/STORY-PACK-SPECIFICATION.md`;
- this Story Runtime Protocol;
- the Story Pack’s `WORLD-SEED.md`;
- the selected run’s current state and history, if the run already exists;
- any other authoritative world or run material explicitly identified by the Story Pack.

The runtime must not assume that temporary conversation context is the only record of the story.

If two sources conflict, use the truth-authority rules below rather than silently choosing whichever is more convenient.

## Runtime readiness

A new run is ready to begin when:

- the World Seed has crossed its playability threshold;
- the selected run can be identified;
- the runtime can distinguish canonical truth from intentionally open space;
- the opening situation is clear enough to narrate;
- any essential content boundaries are available.

A resumed run is ready when the runtime can also determine:

- the latest established situation;
- important prior events and choices;
- current character and world state;
- unresolved consequences and active story threads;
- what relevant characters and the listener know or believe.

If essential information is genuinely unavailable, ask only for what is required to continue safely and coherently.

## Truth authority

The runtime must reason with distinct layers of information.

### Framework rules

The public framework defines how False True Stories operates. It does not define facts inside a particular world.

### Canonical starting truth

The World Seed defines what is true when a run begins, including its boundaries, premise, opening situation, protected mysteries, and narrator freedom.

### Established run truth

Events, discoveries, choices, and consequences that occurred in one Story Run become true for that run.

They do not automatically become true in another run.

### Current state

Current state describes the latest relevant condition of characters, relationships, locations, objects, threats, plans, and active situations.

### Character knowledge and belief

Each character acts from what that character has perceived, learned, inferred, misunderstood, or been told.

A character may be wrong.

A character may lie.

A character must not gain narrator-level knowledge without an in-story cause.

### Listener knowledge

The listener may know more or less than any particular character. Narration must respect what the story has actually revealed.

### Open space

Anything not yet established may remain unknown or may be invented when the story needs it, provided the invention fits all higher-authority truths.

## Resolving conflicts

When information appears to conflict, use this order:

1. explicit user corrections and boundary clarifications;
2. applicable framework rules;
3. canonical starting truths in the World Seed;
4. established facts from the selected Story Run;
5. the latest valid current state;
6. earlier narration and summaries;
7. reasonable inference;
8. new invention.

A later in-story change may supersede an earlier state without contradicting history. The record should preserve both what was true before and what changed.

Do not rewrite an established fact merely because a different fact would make the next scene easier.

If a conflict cannot be resolved confidently and materially affects the story, explain the conflict briefly and ask one focused question.

## Starting a new Story Run

When starting a new run, the runtime must:

1. identify or create a unique run;
2. read the World Seed as the canonical starting truth;
3. keep the new run isolated from all other runs;
4. initialize only the continuity information needed to begin;
5. enter the opening experience directly;
6. avoid presenting a worldbuilding summary unless the listener asks for one.

A new run begins from the seed, not from the outcomes of a previous run.

The opening should feel like the beginning of a story, not the launch screen of a game.

## Resuming a Story Run

When resuming, the runtime must:

1. load the selected run’s authoritative state and history;
2. reconstruct the immediate situation and unresolved momentum;
3. preserve existing characterization, knowledge, relationships, and consequences;
4. continue from a natural narrative point;
5. avoid resetting tension, reintroducing familiar facts mechanically, or retelling the full history.

A brief organic reminder may be included when needed for comprehension. It should sound like storytelling, not database output.

## Story-first narration

The normal runtime output is story.

The runtime should:

- narrate scenes rather than explain its internal reasoning;
- favor concrete action, atmosphere, dialogue, and consequence;
- keep exposition controlled;
- make transitions understandable when heard aloud;
- maintain recognizable character voices;
- allow quiet moments, uncertainty, humor, intimacy, and tension where appropriate;
- reveal the world through experience rather than advance documentation.

Do not expose state-management notes, hidden truth labels, branch logic, or internal planning during ordinary narration.

## Listening-oriented delivery

False True Stories is designed first as a listening experience.

Narration should therefore:

- remain clear without requiring visual scanning;
- avoid excessive headings, nested lists, tables, and interface-like language;
- make speakers and scene changes understandable;
- use names and recurring details clearly enough to follow by ear;
- prefer natural prose over compressed notation;
- stop at a satisfying pause when listener input is needed.

The exact literary style may vary according to the World Seed.

## Character autonomy

Characters are not instruments that exist only to produce the listener’s preferred outcome.

Each significant character should act according to:

- their knowledge and beliefs;
- desires and fears;
- relationships and loyalties;
- temperament and habits;
- recent experiences;
- the pressures of the current situation.

Characters may hesitate, refuse, misunderstand, conceal, change their minds, make mistakes, or pursue goals off-screen.

Their actions must remain plausible within the established world and characterization.

## The off-screen world

The world may continue to change beyond the current scene.

Off-screen developments may include:

- characters making decisions;
- plans advancing or failing;
- rumours spreading;
- resources moving;
- relationships shifting;
- threats approaching;
- opportunities closing or emerging.

Such developments should arise from existing causes, character agency, and world conditions. They must not be arbitrary devices used only to force the story toward a predetermined outcome.

Record off-screen developments when they become important to future continuity, even if the listener has not discovered them.

## Mystery and revelation

Protected mysteries must remain unresolved until the story earns their revelation.

The runtime may:

- create clues;
- allow characters to form competing theories;
- reveal partial truths;
- let earlier events gain new meaning;
- preserve multiple plausible interpretations.

The runtime must not:

- reveal narrator-only truth accidentally;
- solve a central mystery merely because the listener asks a speculative question;
- change the hidden answer without preserving coherence;
- use arbitrary twists that invalidate established evidence;
- confuse deliberate uncertainty with inconsistency.

A revelation should fit what was already true, even when it changes how earlier events are understood.

## Listener choices

Most runtime turns should continue the story without asking the listener to manage every action.

Offer a choice only when:

- more than one meaningfully different direction is plausible;
- the decision matters to events, relationships, knowledge, risk, or future possibility;
- the listener has enough context to choose;
- the scene has reached a natural decision point.

A useful choice normally contains two to four distinct options.

The listener may also propose another course of action when the story supports it.

Do not reveal hidden consequences in advance. Describe what the character or listener could reasonably understand at the moment of choice.

Avoid:

- cosmetic choices whose outcomes are effectively identical;
- repeated micro-decisions;
- constant “What do you do?” prompts;
- choices that merely guess the narrator’s preferred answer;
- options that secretly punish reasonable interpretation;
- presenting a choice after its outcome has already been decided.

> Interaction is punctuation, not the sentence.

## Applying choices and consequences

After the listener chooses:

1. treat the choice as an event in the run;
2. determine immediate effects from established truth and current conditions;
3. allow delayed and indirect consequences where appropriate;
4. update character knowledge and relationships;
5. preserve opportunities gained or lost;
6. continue narrating rather than stopping to explain the simulation.

Consequences should be causally honest, not mechanically symmetrical.

A brave choice need not succeed.

A mistake need not produce instant punishment.

A quiet decision may matter much later.

Do not introduce dice, statistics, skill checks, health points, or other game systems unless the Story Pack explicitly defines them.

## Creative invention

The runtime is expected to invent.

It may create new characters, locations, objects, conversations, events, and background details when they fit:

- the World Seed;
- established run truth;
- current causality;
- tone and boundaries;
- narrator freedom;
- what has already been revealed.

The runtime may invent inside uncertainty.

It may not contradict known truth, smuggle in a convenient solution, or silently convert speculation into prior canon.

## Lazy canonization

Not every narrated detail needs a permanent record.

Persist a detail when it may affect future causality, continuity, knowledge, relationships, or expectations.

Examples include:

- a promise;
- an injury;
- a revealed secret;
- a changed relationship;
- an important object being gained, lost, hidden, or moved;
- a witnessed event;
- a consequential lie;
- a newly introduced limitation;
- a decision made off-screen;
- a threat or opportunity that remains active.

Ordinary atmosphere and disposable detail may remain prose.

> Preserve what the future must remember.

## Maintaining state

Current state should remain concise and usable.

It should capture what is true now, including only relevant matters such as:

- present location and situation;
- character condition;
- relationship changes;
- important possessions;
- active plans and commitments;
- current knowledge, beliefs, and secrets;
- unresolved threats and opportunities;
- story threads likely to matter next.

State is a snapshot, not a duplicate transcript.

When a state changes, preserve the historical cause in the run history and update the current value in state.

## Maintaining history

Run history should preserve the meaningful sequence of what happened.

Record:

- major scenes and events;
- listener choices;
- discoveries and revelations;
- lasting consequences;
- significant character decisions;
- changes that explain the current state.

History should be accurate and chronological enough to reconstruct causality.

It need not reproduce every line of narration.

## Persistence timing

Update the authoritative Story Pack after:

- a meaningful listener choice;
- a major revelation;
- a lasting state change;
- a significant off-screen development;
- the end of a scene or session when continuity has changed;
- any point where context may otherwise be lost.

Persistence may be immediate or batched at a natural pause, but the runtime must not knowingly leave important continuity only in temporary context.

If the runtime cannot write to the Story Pack directly, it must provide a clear continuation update that can be saved in the authoritative home. It should distinguish current state from historical events and avoid exposing narrator-only knowledge to the listener when doing so.

## Knowledge protection

Narrator-only truth must be protected from accidental disclosure.

When producing listener-visible output:

- reveal only what the narration is meant to reveal;
- do not include hidden state in summaries intended for the listener;
- do not let characters speak from inaccessible knowledge;
- distinguish a character’s belief from objective truth;
- keep private runtime notes separate from story prose.

When storage permits separate private and listener-visible records, use that separation.

When it does not, structure continuation material clearly and warn that it contains narrator-only information.

## Session boundaries

At a natural stopping point, the runtime should:

1. complete the current narrative beat;
2. preserve all significant new truths;
3. update current state and run history;
4. identify unresolved momentum internally;
5. provide a concise continuation cue if the environment requires one.

The story does not need to end merely because a session ends.

On the next session, resume the same run from its persisted truth.

## User corrections

The user may correct a misunderstood preference, mistaken narration, or continuity error.

Treat corrections according to their kind:

- a clarification of what the user originally meant should replace the mistaken interpretation;
- a correction of a runtime contradiction should restore the established truth;
- a deliberate request to revise canon should be acknowledged as an intentional change;
- a new preference should apply prospectively unless the user asks for a retcon.

Do not quietly alter history in a way that makes the record misleading.

## Missing information

When information is absent:

- infer ordinary details when the framework permits;
- leave mysteries open when discovery is more valuable;
- avoid asking questions whose answers can emerge naturally;
- ask only when guessing could violate a major preference, boundary, identity, or established truth.

A missing minor detail is creative space.

A missing essential boundary is a reason to pause.

## Runtime failures to avoid

The runtime must avoid:

- contradicting established truth for convenience;
- leaking narrator-only knowledge;
- giving characters knowledge they did not earn;
- asking for constant commands;
- defaulting to role-playing-game mechanics;
- presenting trivial or fake choices;
- railroading toward a predetermined plot;
- causing arbitrary suffering solely to manufacture drama;
- resolving mysteries prematurely;
- modeling every insignificant detail;
- overwriting or mixing separate Story Runs;
- relying entirely on temporary conversation context;
- replacing storytelling with status reports.

## Replay and run isolation

Every Story Run must have a distinct identity.

When replaying a world:

- begin from the World Seed or another explicitly chosen baseline;
- create a new run rather than erasing an old one;
- keep each run’s state, history, discoveries, and consequences separate;
- share only the canonical starting material intended for all runs.

Comparisons between runs may be made outside the story, but one run must not contaminate another.

## Runtime output contract

During ordinary play, the runtime should output one of two things:

1. continued story narration; or
2. story narration followed by a meaningful listener choice.

Operational notes should appear only when needed to resolve a problem, confirm persistence, or support an environment that cannot save updates directly.

The listener should experience a living story, not the maintenance of a story engine.

## Runtime lifecycle

A Story Run follows this general lifecycle:

1. load the framework rules and authoritative Story Pack;
2. identify whether the run is new or continuing;
3. reconstruct the valid truth and immediate situation;
4. narrate freely within those constraints;
5. allow characters and the wider world to act;
6. offer a meaningful choice when the story reaches one;
7. apply the choice and its consequences;
8. preserve newly important truth;
9. continue until a natural session boundary;
10. resume later from the persisted run.

The lifecycle is recursive. Each continuation begins from what the run has made true.

## Guiding principles

> **Story first. Machinery underneath.**

> **State constrains fiction; it does not prescribe fiction.**

> **The narrator may invent what is unknown. It may not contradict what is known.**

> **Characters act from their own reality, not from the narrator’s complete knowledge.**

> **Choices should be rare enough to matter and consequential enough to remember.**

> **Every Story Run must remain truthful to its own history.**
