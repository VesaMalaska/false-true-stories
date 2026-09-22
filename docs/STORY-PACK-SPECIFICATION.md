# False True Stories — Story Pack Specification

This specification defines the minimum portable container for one False True Stories world and its story runs.

It describes what information a Story Pack must preserve. It does not require a particular language model, storage provider, application, or rigid directory structure.

## Purpose

The public False True Stories repository contains the reusable framework.

A Story Pack contains one particular fictional world created with that framework.

The separation is:

```text
Public False True Stories framework
                ↓
         World Seed creation
                ↓
       Separate Story Pack
                ↓
      One or more Story Runs
```

The public framework may be shared by everyone.

A Story Pack may remain private, be shared with selected people, or be published separately by its creator.

## Core principle

> The framework defines how stories work.  
> The Story Pack contains what is true in one particular world.

Private story information, listener choices, unpublished mysteries, and evolving story history do not belong in the public framework repository.

## Key concepts

### World Seed

The World Seed contains the minimum truth required to begin the story.

It establishes matters such as:

- the core premise;
- protagonists or listener position;
- reality boundaries;
- tone and permissible danger;
- important relationship dynamics;
- canonical starting truths;
- intentionally protected mysteries;
- narrator freedom;
- the opening situation.

The World Seed is deliberately incomplete. It gives the story enough direction to begin while preserving space for discovery.

### Story Pack

A Story Pack is the portable collection of information belonging to one fictional world.

At first, it may contain only a completed `WORLD-SEED.md`.

As stories are played, the pack may also contain:

- individual Story Runs;
- established truths;
- current character and world state;
- important event history;
- listener choices and their consequences;
- character knowledge, beliefs, and secrets;
- optional supporting world material.

A Story Pack should grow only when the story creates a genuine need for more persistent information.

### Story Run

A Story Run is one evolving history beginning from the Story Pack’s World Seed.

Different runs may begin from the same starting truth and develop differently.

A Story Run contains only what became true in that particular history. Facts established in one run must not silently appear in another run.

## Separation from the public framework

The public framework repository contains:

- general concepts and principles;
- creation and runtime protocols;
- launcher prompts;
- reusable templates;
- public examples;
- provider-specific usage guidance.

A Story Pack contains:

- one specific World Seed;
- world-specific characters, locations, mysteries, and truths;
- run-specific choices, consequences, and history;
- private or unpublished material belonging to that world.

The Story Pack should not modify or redefine the False True Stories framework.

The framework should not require a creator to publish their Story Pack.

## Minimum playable Story Pack

Before the first Story Run begins, a Story Pack requires only:

```text
WORLD-SEED.md
```

The World Seed must have crossed the playability threshold defined in `WORLD-SEED-GENERATION.md`.

It must give the runtime enough information to understand:

- what kind of experience this is;
- who or what the story follows;
- what kind of reality belongs to the story;
- the intended tone and danger;
- what truths and boundaries must be preserved;
- which important matters remain intentionally unknown;
- where or how the story begins.

No empty character, location, lore, inventory, timeline, or state files are required before the story needs them.

## Recommended portable structure

The smallest recommended structure is:

```text
my-story-pack/
└── WORLD-SEED.md
```

After a Story Run begins, the pack may grow into:

```text
my-story-pack/
├── WORLD-SEED.md
└── runs/
    └── first-run/
        ├── STATE.md
        └── HISTORY.md
```

The names `STATE.md`, `HISTORY.md`, and `first-run` are recommended conventions rather than universal technical requirements.

The semantic responsibilities matter more than the exact filenames.

A storage environment that cannot represent folders may keep the same information in another clearly distinguishable form.

## World Seed responsibility

`WORLD-SEED.md` owns the starting truth shared by Story Runs created from that seed.

Before the first run begins, the creator may revise the World Seed freely.

Once a run has begun, its starting truth should not be silently rewritten. Otherwise earlier actions may lose their meaning or become contradictory.

If a material correction is necessary, it must be made explicitly. Existing runs must not be retroactively reinterpreted without the creator’s knowledge.

A substantially changed World Seed may be treated as a new version of the Story Pack for future runs.

## Run state responsibility

A Story Run needs a persistent representation of what is currently true.

The run state may include:

- the current situation;
- character locations and conditions;
- important possessions;
- relationships and promises;
- established facts;
- active dangers or opportunities;
- character knowledge and beliefs;
- unresolved story threads;
- decisions whose consequences remain pending.

The state should record only information that matters to continuity or future causality.

It should not attempt to convert every descriptive detail into structured data.

> State constrains fiction; it does not prescribe fiction.

The Story Runtime Protocol will define when and how run state is updated.

## History responsibility

A Story Run should preserve enough history to explain how its current state came to exist.

History may include:

- meaningful listener choices;
- important character decisions;
- significant events;
- discoveries;
- injuries, losses, promises, and relationship changes;
- facts that became established;
- consequences that may matter later.

History is not required to reproduce every word of narration.

Its purpose is continuity and causality, not complete transcription.

The runtime may preserve full chapters or session transcripts separately, but those are optional unless the chosen experience requires them.

## Truth categories

A Story Pack should preserve the distinction between different kinds of information.

### Canonical starting truth

Facts defined by the World Seed or other accepted baseline material.

### Established run truth

Facts that became true during one Story Run and must remain consistent within that run.

### Current story state

Facts that describe the present situation but may naturally change as events continue.

### Character knowledge and belief

What a particular character knows, believes, suspects, misunderstands, or has been told.

Character knowledge is not automatically the same as world truth.

### Listener knowledge

What the listener has been allowed to discover.

The narrator may know truths that neither the listener nor the characters know.

### Open space

Matters that have not yet been defined and may be invented when the story needs them.

An undefined detail is not an error. It is creative space.

## Run isolation

Each Story Run is its own history.

The runtime must not copy established truths, choices, relationships, discoveries, or consequences from one run into another unless those facts already belong to their shared starting truth.

For example:

- a character injured in Run A is not automatically injured in Run B;
- a secret discovered in Run A remains unknown in Run B unless discovered there;
- a relationship developed in Run A does not already exist in a fresh run;
- an object destroyed in Run A remains available in Run B if it existed in the shared baseline.

Runs may diverge as widely as their histories justify.

## Lazy expansion

A Story Pack should not begin as an encyclopedia.

New files or sections should be created only when they improve continuity, navigation, portability, or maintainability.

Possible later additions include:

```text
characters/
locations/
world/
sessions/
assets/
```

These are optional.

A Story Pack should not create empty directories or placeholder documents merely because they might become useful someday.

A useful rule is:

> Do not model something merely because it can be modeled. Preserve it when the story needs to remember it.

## One authoritative home

Every active Story Pack should have one clearly identified authoritative home.

Possible authoritative homes include:

- a private Git repository;
- a local folder;
- Google Drive;
- a ChatGPT Project;
- a Claude Project;
- another compatible file or project environment.

Copies may be exported or attached elsewhere for use, but those copies should be treated as snapshots unless authority is explicitly transferred.

Two independently edited copies must not silently act as equal sources of truth.

When moving a Story Pack to a new environment, the creator should decide which copy becomes authoritative before continuing the story.

## Provider neutrality

A valid Story Pack must not depend on one specific language-model provider.

The pack should use ordinary, understandable language and portable files whenever practical.

Markdown is the preferred initial format because it is:

- human-readable;
- understandable by capable language models;
- compatible with Git, local folders, and cloud drives;
- easy to copy and edit;
- independent of proprietary authoring software.

A provider may impose practical limitations on attachments, context size, or file updates. Provider-specific guidance may explain how to work within those limitations, but it must not redefine the Story Pack’s truth model.

## Semantic requirements, not rigid filenames

This specification defines information responsibilities rather than an inflexible schema.

A Story Pack needs a World Seed, but an environment does not become invalid merely because it renames the file or combines several responsibilities into one document.

Similarly, a large Story Pack may split information across several files without changing the underlying model.

A pack is valid when:

- its starting truth can be identified;
- each Story Run can be distinguished;
- current run state can be identified;
- important history and established truths can be recovered;
- character knowledge is not confused with world truth;
- the authoritative copy is known.

The recommended filenames exist to improve portability and shared understanding.

## Privacy

A Story Pack may contain:

- unpublished creative material;
- hidden mysteries;
- private listener choices;
- personal preferences;
- story content inspired by private experiences;
- information that should not be exposed to other players.

Story Packs should therefore be considered private unless their creator deliberately publishes or shares them.

The public False True Stories framework must never require access to private Story Packs.

## Story Pack lifecycle

A basic Story Pack lifecycle is:

1. Create a World Seed using the World Seed Generation Workflow.
2. Save the generated `WORLD-SEED.md` in a separate Story Pack.
3. Choose one authoritative home for that pack.
4. Begin a new Story Run from the World Seed.
5. Preserve important state, choices, and established truths as the run develops.
6. Resume the run from its own state and history.
7. Create a separate run when beginning again from the same seed.
8. Export or move the pack only with a clear decision about which copy remains authoritative.

## Readiness

A Story Pack is ready to begin its first run when:

- a complete World Seed exists;
- the World Seed is marked ready to play;
- the runtime can access and understand it;
- the authoritative Story Pack location is known;
- no missing preference would force the runtime to guess something capable of ruining the intended experience.

A Story Run is ready to resume when the runtime can identify:

- which run is being continued;
- its current situation;
- its established truths;
- the important history leading to that situation;
- the knowledge and boundaries relevant to the next scene.

The Story Runtime Protocol will define the precise runtime handoff and update process.

## Non-goals

This specification does not define:

- a database schema;
- a mandatory Git workflow;
- a required cloud provider;
- a software execution engine;
- a complete narration protocol;
- a predefined plot;
- a branching story tree;
- a synchronization system for competing authoritative copies;
- an exhaustive worldbuilding structure;
- a requirement to publish private stories.

Those responsibilities either belong to other False True Stories documents or remain decisions for the Story Pack creator.

## Relationship to the Story Runtime Protocol

This specification defines what the story-specific container must preserve.

The future Story Runtime Protocol will define how a language model:

- reads the Story Pack;
- begins a new run;
- resumes an existing run;
- tells the story;
- introduces meaningful choices;
- promotes important details into established truth;
- updates current state and history;
- preserves knowledge boundaries;
- prepares continuation information at the end of a session.

The Story Pack Specification defines the container.

The Story Runtime Protocol defines the behavior operating inside it.

## Guiding principle

> Begin with one World Seed.  
> Add only what the story needs to remember.  
> Keep every run truthful to its own history.
