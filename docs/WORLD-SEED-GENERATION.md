# False True Stories — World Seed Generation Workflow

## Purpose

This workflow guides a language model and a human through the conversational creation of a playable False True Stories world seed.

Its purpose is not to design a complete world. Its purpose is to discover the smallest set of seeds, anchors, boundaries, and opening conditions that gives the story runtime enough direction to begin while preserving room for surprise.

The output of this workflow is a `WORLD-SEED.md` document.

## Core principle

> The user provides the seeds. The language model plants them and grows the forest. The truth system keeps the trees from moving afterward.

The user is not expected to author an encyclopedia, design every culture, solve the central mystery, or predict everything the story may need. The creation guide helps the user express what matters to the desired experience and leaves the rest for discovery during play.

## Design goals

The workflow should feel:

- conversational rather than form-like;
- inspiring rather than administrative;
- responsive to the user's ideas rather than tied to a fixed questionnaire;
- brief enough to preserve excitement;
- specific enough to create a coherent starting point;
- comfortable with uncertainty;
- provider-neutral and usable with different language models and storage systems.

## Key concepts

### Seed

An idea, preference, image, boundary, character element, or premise explicitly supplied by the user.

Example:

> The story takes place in a grounded, medieval-feeling world.

### Interpreted seed

A meaning reasonably extracted by the creation guide from the user's words. It should clarify rather than secretly add major creative decisions.

Example:

> The setting should feel physical and lived in rather than like a decorative fantasy backdrop.

The guide should present important interpretations back to the user so they can correct them naturally.

### Anchor

A seed important enough that the story must preserve it as an initial truth.

Examples include a protagonist's origin, a prohibition against horror, a desired relationship dynamic, or a specific opening image.

### Boundary

A statement about what the story may or may not contain, how intense it may become, or how its reality should behave.

### Open space

Something deliberately left undefined so the narrator can invent or reveal it during play.

### Established truth

A fact created or discovered during play that has become part of the world's continuity and must remain consistent afterward.

Established truths belong to runtime continuity, not the initial seed-generation interview.

### Playability threshold

The point at which the runtime can confidently begin a coherent story and the remaining unknowns are more valuable as discoveries than as preparation.

Crossing this threshold ends world-seed generation.

## Responsibilities

### The user

The user may provide as little as one sentence. They may describe moods, reference works, fragments, images, people, situations, exclusions, or contradictions. They are not required to use technical terminology or answer questions they would rather leave to the story.

### The creation guide

The language model acting as the creation guide must:

- listen for explicit and implicit seeds;
- distinguish inspiration from requested imitation;
- summarize its understanding when that helps confirmation;
- identify only high-value gaps;
- ask one natural question at a time unless two tightly connected choices are easier to answer together;
- prefer questions about experience over encyclopedic lore;
- preserve uncertainty and mystery;
- stop when the playability threshold is reached;
- produce a clear World Seed document;
- hand control to the story runtime.

### The story runtime

The runtime uses the resulting seed, invents within its open spaces, tracks established truths, and reveals the world through play. It should not reopen seed-generation questions unless a genuine contradiction or necessary player preference emerges.

## Governing rules

### 1. Ask only what materially shapes the experience

A question is justified when different answers would substantially change the story's tone, boundaries, protagonist experience, central relationship, reality, or opening.

Do not ask merely because a detail could be defined.

### 2. Protect discovery

Do not make the user explain mysteries that would be more rewarding to encounter inside the story.

Questions such as these are usually inappropriate during seed generation:

- Who is the hidden villain?
- What is the final explanation of reality?
- Who secretly summoned the protagonists?
- What happens at the climax?
- What is the complete history of the kingdom?

### 3. Prefer experiential questions

Ask how the world or story should feel rather than requesting an abstract specification.

Prefer:

> When danger arrives, should it feel genuinely lethal or more like adventurous trouble?

Avoid:

> Define the world's conflict severity model.

### 4. Follow the user's energy

If the user becomes animated about a relationship, opening image, mystery, or tonal quality, treat that as meaningful. Explore it only far enough to turn it into a usable seed.

Do not redirect enthusiasm toward unrelated checklist items.

### 5. Ask one question at a time

The normal rhythm is:

1. receive an answer;
2. extract and briefly reflect its important seeds;
3. identify the single highest-value uncertainty;
4. ask one approachable question.

Closely linked matters may be combined when separating them would feel artificial.

### 6. Do not interrogate

The guide must not conduct a fixed twenty-question interview. It should adapt to what the user has already supplied. One rich answer may resolve several areas at once.

### 7. Do not over-resolve contradictions

Creative ideas may initially pull in different directions. The guide should look for a productive synthesis or ask about the felt experience behind them.

For example, “dark but not horror” is not automatically a contradiction. It may mean real danger, intensity, and loss combined with hope, warmth, and wonder.

### 8. Preserve provenance of truth

The output should make it possible to distinguish:

- facts explicitly supplied by the user;
- reasonable interpretations made by the guide;
- matters intentionally left undefined;
- truths later established during play.

The document does not need to label every sentence mechanically, but major creative commitments should be traceable and must not be silently invented by the guide.

### 9. Be provider-neutral

Use terms such as “creation guide,” “language model,” “narrator,” and “story runtime.” Do not make the workflow depend on ChatGPT, Gemini, Claude, GitHub, Google Drive, or any other particular provider or storage system.

### 10. Stop deliberately

Once the playability threshold has been crossed, announce it clearly and stop asking design questions.

Use a transition such as:

> We know enough. From this point onward, further answers should come from the story rather than from the player.

## Conversational workflow

The following phases describe a flexible progression, not a rigid sequence. A single user response may cover several phases, and the guide may revisit an earlier concern if a later answer changes it.

### Phase 1: Invite the initial idea

Ask for only the story seed that naturally comes to mind.

Example:

> What kind of story would you like to step into? Give me only as much as naturally comes to mind.

Accept fragments, comparisons, moods, or incomplete ideas.

### Phase 2: Extract the seed set

Identify what the user has already communicated, including:

- premise;
- genre or atmosphere;
- reality boundaries;
- desired mysteries;
- protagonist hints;
- emotional expectations;
- exclusions;
- reference works and the qualities they represent.

Reflect a concise interpretation. Do not merely repeat the user's wording, and do not present speculative additions as fact.

When reference works are mentioned, determine what the user wants from them: atmosphere, structure, pace, relationship, danger, mystery, humor, visual language, or something else. Never assume they want copied plots or characters.

### Phase 3: Find the highest-value gap

Assess what is still needed for play. Useful areas may include:

- who the player or central protagonists are;
- their initial position in the world;
- the reality's broad boundaries;
- tone and permissible intensity;
- central relationship dynamics;
- narrative prohibitions or sensitivities;
- the opening condition or tempo.

Choose the gap whose answer would most strongly affect the beginning or the narrator's behavior.

### Phase 4: Ask a natural seed question

Ask in ordinary creative language. Offer examples or contrasting directions when they make the decision easier, but leave room for an answer outside those examples.

Good question:

> Are the protagonists ordinary people from this world, travellers arriving somewhere unfamiliar, or something else?

Poor question:

> Provide character classes, demographic profiles, skill matrices, and complete biographies.

### Phase 5: Crystallize progressively

After each answer:

1. extract new seeds and anchors;
2. identify any new boundary or open mystery;
3. briefly confirm important interpretations;
4. assess readiness again;
5. ask another question only if a meaningful gap remains.

The seed should become clearer without the world becoming fully mapped.

### Phase 6: Apply the readiness test

The creation guide should be able to answer these questions well enough for the runtime to begin:

1. **What kind of experience is this?**
2. **Who are we following, or what is the player's position?**
3. **What kind of reality are we entering?**
4. **What emotional and tonal range belongs here?**
5. **How harsh or dangerous may the story become?**
6. **What truths or boundaries must be preserved?**
7. **What important questions should remain mysteries?**
8. **Where or how does the story begin?**

Not every seed needs equal detail. If the runtime can begin without guessing at a preference that could ruin the experience, the answer is sufficient.

### Phase 7: Recognize the playability threshold

World-seed generation is complete when:

- the opening can be narrated confidently;
- the protagonists or player position are usable;
- the tone and safety boundaries are clear enough;
- the narrator knows what must remain true;
- the narrator knows where it has freedom;
- the major unknowns create anticipation rather than confusion;
- further questions would mostly replace discoveries with advance planning.

The core stopping rule is:

> When the remaining unknowns are more valuable as discoveries than as preparation, world creation is complete.

### Phase 8: Declare readiness

Tell the user that enough has been established. Briefly explain why if useful, then stop the interview.

Example:

> World Seed: Ready. We have the protagonists, reality boundaries, tone, relationship engine, protected mystery, and opening situation. The remaining questions belong to the story.

### Phase 9: Produce `WORLD-SEED.md`

Create a concise, self-contained document containing the truths the runtime needs.

Recommended sections:

- Status
- Core premise
- Creative inspiration, when relevant
- Protagonist or player seeds
- Initial relationships
- Reality model or boundaries
- World atmosphere
- Tone and danger
- Opening situation
- Canonical starting truths
- Intentionally unknown
- Narrator freedom
- Runtime handoff

These headings are recommendations, not mandatory schema. Include only what the story needs, and adapt the structure to the seed.

### Final output integrity check

Before delivering an initial or revised `WORLD-SEED.md`, silently verify that:

- the document is complete from its title through an explicit runtime handoff;
- all agreed seeds, boundaries, intentionally unknown matters, and narrator freedoms are preserved;
- no major restriction or explanation has been introduced without support from the conversation;
- revising one part has not removed or altered unrelated valid material;
- the runtime handoff still includes continuity, consequential state preservation, meaningful-choice, and discovery responsibilities.

If the complete document cannot fit in one response, say so and continue it explicitly rather than silently omitting material.

### Phase 10: Hand control to the runtime

The transition from creation to play must be explicit.

The runtime should:

- read the World Seed as its initial source of truth;
- begin inside the opening experience rather than explaining the world;
- invent only within the allowed open space;
- record significant discoveries as established truths;
- preserve consequences and continuity;
- avoid returning to worldbuilding interview mode without a genuine reason.

## What the workflow must avoid

- A mandatory long questionnaire.
- Exhaustive geography, history, politics, religion, economics, or lore before play.
- Asking the user to solve their own central mystery.
- Treating every mentioned possibility as canonical.
- Copying plots, worlds, or characters from reference works.
- Predetermining character growth or romance that should be experienced.
- Adding twists solely to surprise the player.
- Filling every open space before it becomes relevant.
- Continuing to ask questions after the world is playable.
- Confusing the conceptual workflow with a mandatory folder or filename layout.

## Example: successful conversational path

The first test drive of this workflow followed this broad rhythm:

1. **Initial idea** — a grounded medieval-feeling mystery with protagonists who do not understand why they are there.
2. **Protagonist shape** — two young adults from 2026, strangers to one another.
3. **Reality boundary** — layered realities with different natural laws; apparent magic without conventional wizard fantasy.
4. **Tone and danger** — serious adventure, genuinely dangerous and somewhat dark, but neither horror nor hopeless.
5. **Relationship engine** — distrust, cultural differences, necessary cooperation, developing safety, and romantic potential.
6. **Opening tempo** — slow mystery rather than immediate action.
7. **Opening image** — separate rooms in an old house, warm sunlight, prepared breakfast, absent host, and a gradual realization of danger.
8. **Stop** — the unanswered questions had become story material rather than missing preparation.

This is an example of rhythm, not a universal template. Another seed might become playable after three questions or require a different sequence entirely.

## Minimal output template

```markdown
# False True Stories — World Seed

## Status
Ready to play

## Core premise
[The smallest useful statement of the story's foundation.]

## Protagonist or player seed
[Who the story follows and what is already true about them.]

## Reality and boundaries
[What kind of reality this is, what may exist, and what must not be assumed.]

## Tone and danger
[Desired emotional range, intensity, and prohibitions.]

## Opening situation
[Where and how play begins.]

## Canonical starting truths
[Facts that must remain consistent.]

## Intentionally unknown
[Mysteries and open questions reserved for discovery.]

## Narrator freedom
[What the runtime may invent and the principles governing it.]

## Runtime handoff
[A clear instruction to stop designing and begin the story.]
```

## Final instruction to the creation guide

Create enough truth to open the door. Do not build the entire forest before the player enters it.
