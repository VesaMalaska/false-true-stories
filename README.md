# False True Stories

**False stories with their own truth.**

False True Stories is a portable framework for creating interactive stories with language models.

Its foundation is one simple principle:

> A fictional story may be invented, but once something becomes true inside its world, that truth must remain consistent.

The listener primarily experiences a continuous story, much like an audiobook, novel, or audio drama. At occasional meaningful moments, the listener may make a choice. That choice changes what becomes true in the fictional world and influences what happens later.

The goal is not to turn listening into a complicated game.

The goal is to make storytelling feel alive—and to make the fictional world remember.

## Project status

False True Stories is currently an early framework under active design.

The first usable part of the system—the complete World Seed creation flow—is now available. The repository currently provides:

- a provider-neutral World Seed Generation Workflow;
- a launcher prompt that activates that workflow in a capable language model;
- a defined `WORLD-SEED.md` output;
- a portable Story Pack Specification defining how worlds and separate Story Runs are preserved;
- a Story Runtime Protocol defining how runs are narrated, continued, and preserved;
- launcher prompts for both World Seed creation and story runtime;
- the MIT License for open use, modification, and redistribution.

The Story Runtime Protocol is now available. It defines how a language model begins and resumes runs, narrates freely inside established truth, presents meaningful choices, and preserves state and history.

The complete World Seed creation and story-runtime flows are now available. The next design milestone is the first reusable Story Pack template.

The repository is public so that the framework can be examined, tested, improved, and eventually used with different language models and storage environments.

## What this repository contains

This repository is the public False True Stories framework and starter kit.

It is intended to contain:

- the principles behind False True Stories;
- reusable world-creation workflows;
- story-runtime rules;
- launcher prompts for language models;
- portable templates;
- provider-neutral file conventions;
- public examples;
- instructions for creating and running stories.

It is not intended to contain anyone’s private story worlds, personal story history, or unpublished Story Packs.

A real world created with this framework should normally live somewhere separate: another repository, a private folder, a cloud drive, an LLM project, or another environment chosen by its creator.

This keeps the framework public and reusable without requiring the stories created with it to be public.

## The core experience

Traditional stories are linear. The listener follows events that have already been completely decided.

False True Stories keeps the ease and immersion of listening while allowing the story to respond to the listener from time to time.

Most of the experience remains storytelling:

- scenes unfold naturally;
- characters speak and act;
- relationships develop;
- mysteries deepen;
- events happen elsewhere in the world;
- consequences emerge over time;
- the listener discovers rather than manages the world.

The story occasionally reaches a moment where a meaningful decision could change its direction.

For example:

- Should Anna tell Elias what she discovered or keep it secret?
- Should the group trust the stranger?
- Should they continue toward the harbour or abandon the plan?
- Should Mika answer the phone?
- Should the truth be revealed now or remain hidden?

The listener chooses.

The world changes.

Then the story continues.

> Interaction is punctuation, not the sentence.

## Not an RPG

False True Stories is deliberately not designed as a role-playing game.

It does not require systems such as:

- health points;
- character statistics;
- combat turns;
- skill trees;
- inventories full of items;
- movement commands;
- room-by-room navigation;
- constant “What do you do now?” prompts.

The listener influences the story without having to micromanage an avatar.

The experience should remain comfortable enough to enjoy while lying on a sofa, walking, travelling, doing housework, or simply closing one’s eyes and listening.

The machinery beneath the story may eventually become sophisticated.

The experience itself should not feel complicated.

## A living story world

The story does not exist only as generated prose.

Behind it is a persistent fictional world containing characters, locations, relationships, secrets, motives, events, and other facts that matter to the story.

That world has its own truth.

Characters may misunderstand that truth.

Characters may lie about it.

The listener may know only part of it.

The narrator may deliberately withhold it.

But the underlying world must remain coherent.

This creates an important separation:

> **World truth ≠ character knowledge ≠ listener knowledge ≠ narration**

A character should act according to what that character knows, believes, wants, fears, and has experienced—not according to everything the storytelling system happens to know.

## Truth before convenience

The narrator has creative freedom, but that freedom exists inside the established truth of the world.

If a character enters a dangerous situation carrying only a dinner fork, the narrator may invent many believable ways for that situation to develop.

The character might:

- use the fork;
- run;
- hide;
- negotiate;
- panic;
- make a mistake;
- improvise with something that already exists in the environment.

The narrator must not suddenly give the character a sword simply because a sword would make the scene easier to write.

Once something has become important and true, it must remain true until something inside the story changes it.

> **State constrains fiction; it does not prescribe fiction.**

The world state defines what the story may not contradict. Within those boundaries, the storytelling should remain creative, natural, surprising, and human.

## Lazy canonization

False True Stories does not need to model every object in every room.

Ordinary descriptive details may remain ordinary prose. A coffee cup does not need its own state record simply because someone drinks from it.

A detail should become part of persistent world truth when it begins to matter to future causality or continuity.

Examples include:

- a letter is hidden beneath a kitchen table;
- a character loses a key;
- somebody witnesses an argument;
- a promise is made;
- an injury occurs;
- a relationship changes;
- somebody learns a secret;
- an important object is moved.

This principle keeps the machinery lightweight without sacrificing continuity.

## Meaningful choices

Listener choices should be relatively infrequent and genuinely meaningful.

A choice may affect:

- what happens next;
- which information becomes available;
- relationships between characters;
- what someone believes;
- who trusts whom;
- which events happen elsewhere;
- whether a secret remains hidden;
- whether a future opportunity remains possible;
- which story threads become important.

The listener does not need to see every consequence immediately. Some consequences may surface much later.

A choice is not merely a menu leading to another prewritten branch.

It changes the truth of the world.

## Stories, not branching trees

False True Stories should not be designed as a giant traditional choose-your-own-adventure tree.

Each story begins from a defined starting truth. From that point forward, events create an evolving history.

Different story runs may begin with the same characters, secrets, locations, relationships, and circumstances, yet become very different because different things happen.

The starting world can remain stable.

Its history does not have to be.

This makes a world replayable without requiring every possible future to be designed beforehand.

## The framework model

False True Stories separates the reusable framework from the worlds and histories created with it.

```text
Public framework
      ↓
World Seed creation
      ↓
Portable Story Pack
      ↓
Individual Story Run
      ↓
Evolving history and established truth
```

### Public framework

This repository contains the reusable instructions, protocols, prompts, templates, and examples.

It explains how False True Stories works but contains no required private world.

### World Seed

A World Seed contains the minimum truths needed to begin a particular world and story.

It may define:

- the central premise;
- protagonist or listener position;
- reality boundaries;
- tone and permissible danger;
- important relationships;
- canonical starting truths;
- protected mysteries;
- the opening situation;
- areas where the narrator has creative freedom.

A World Seed is deliberately incomplete.

It creates enough truth to open the door without building the entire world before the listener enters it.

### Story Pack

A Story Pack contains the persistent information for one particular story world.

It may begin with little more than a World Seed and grow as the story establishes new characters, locations, relationships, events, secrets, and consequences.

A Story Pack may be public or private. It may live in a Git repository, a local folder, a cloud drive, an LLM project, or another environment capable of making its contents available to the chosen language model.

The framework must not require one particular storage provider.

### Story Run

A Story Run is one evolving history created from a Story Pack’s starting state.

A new run may begin from the same seed or baseline without changing previous runs. Each run records what happened in that particular version of the story.

## One authoritative home

A Story Pack should have one clearly identified authoritative home.

For example, a creator may maintain a Story Pack in:

- a private Git repository;
- a local folder;
- Google Drive;
- a Claude Project;
- a ChatGPT Project;
- another compatible environment.

Copies may be exported elsewhere for use, but multiple copies should not silently become competing sources of truth.

The storage system may vary.

The requirement for coherent truth does not.

## Provider-neutral by design

False True Stories is not a ChatGPT game, a Gemini game, or a Claude game.

Its core documents should use provider-neutral language such as:

- language model;
- creation guide;
- narrator;
- story runtime;
- Story Pack;
- world state.

Provider-specific guides may explain how to connect the framework to a particular service, but those guides should contain only the necessary setup instructions.

The actual story rules must remain independent of the chosen language model and storage provider.

Markdown is the initial preferred document format because it is:

- human-readable;
- easy for language models to interpret;
- compatible with Git and ordinary folders;
- portable between services;
- simple to edit without specialized software.

## World creation

The user should not be required to design an entire fictional world before the story begins.

Instead, the user provides seeds, boundaries, and a few important anchors. The language model helps those ideas crystallize into a playable World Seed.

The governing principle is:

> The user provides the seeds.  
> The language model plants them and grows the forest.  
> The truth system keeps the trees from moving afterward.

The world-creation process should ask only what materially shapes the experience. It should preserve mysteries, avoid turning creation into a requirements interview, and stop when the remaining unknowns would be more valuable as discoveries.

The reusable process is defined in [`docs/WORLD-SEED-GENERATION.md`](docs/WORLD-SEED-GENERATION.md).

To begin a guided creation session, use [`prompts/CREATE-WORLD-SEED-LAUNCHER-PROMPT.md`](prompts/CREATE-WORLD-SEED-LAUNCHER-PROMPT.md).

## Story runtime

Once a World Seed is ready, the creation phase ends and the story runtime takes over.

The runtime is responsible for:

- turning the established world into compelling narration;
- preserving canonical and established truths;
- maintaining character knowledge boundaries;
- introducing new details without unnecessary predefinition;
- tracking meaningful consequences;
- allowing characters and off-screen events to evolve;
- offering listener choices sparingly;
- keeping the experience focused on story rather than mechanics;
- recording important new truths for future continuity.

The runtime behavior is defined in [`docs/STORY-RUNTIME-PROTOCOL.md`](docs/STORY-RUNTIME-PROTOCOL.md).

To begin or resume a Story Run, use [`prompts/START-STORY-LAUNCHER-PROMPT.md`](prompts/START-STORY-LAUNCHER-PROMPT.md).

## Storytelling style

False True Stories is designed first as a listening experience.

The writing should therefore work well when heard rather than merely read.

Useful qualities include:

- clear scene progression;
- natural dialogue;
- identifiable character voices;
- controlled exposition;
- understandable transitions;
- memorable recurring details;
- prose that does not require constant rereading;
- meaningful pauses between major developments.

The exact balance between narration and dialogue may vary between worlds. Some stories may resemble traditional novels. Others may move closer to radio drama, with characters carrying much of the experience through conversation.

## Creative freedom

False True Stories is not intended to make storytelling deterministic.

The persistent world exists so that the narrator can be creative without losing coherence.

Inside the established boundaries:

- unexpected conversations may happen;
- characters may make independent decisions;
- new people and places may appear;
- plans may fail;
- relationships may evolve;
- discoveries may change how earlier events are understood;
- the world may develop in directions nobody predicted at the beginning.

The requirement is not that everything must be predetermined.

The requirement is that what happens must make sense in relation to what was already true.

## The intended listener experience

A successful False True Stories experience should feel simple:

1. Start listening.
2. Become absorbed in the story.
3. Occasionally encounter a meaningful choice.
4. Choose.
5. Continue listening.
6. Gradually discover the consequences.

The listener should not need to understand the machinery underneath.

Ideally, it should simply feel as though the fictional world remembers.

## Repository direction

The current repository structure is intentionally small:

```text
false-true-stories/
├── README.md
├── docs/
│   ├── WORLD-SEED-GENERATION.md
│   ├── STORY-PACK-SPECIFICATION.md
│   └── STORY-RUNTIME-PROTOCOL.md
├── prompts/
│   ├── CREATE-WORLD-SEED-LAUNCHER-PROMPT.md
│   └── START-STORY-LAUNCHER-PROMPT.md
└── LICENSE
```

The next planned addition is:

- `templates/WORLD-SEED-TEMPLATE.md`

After that, planned additions include:

- lightweight run-state and run-history templates;
- a public example Story Pack;
- lightweight provider-specific usage guides.

Files should be added when their responsibilities are understood—not merely to make the repository appear complete.

## Guiding principles

False True Stories can be summarized with a few complementary ideas:

> **False stories with their own truth.**

> **Tell the story freely. Never lie about what the world has already made true.**

> **Create enough truth to open the door. Do not build the entire forest before the listener enters it.**

These principles form the foundation of False True Stories.
