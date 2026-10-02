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
- a Story Environment Setup workflow establishing authority, access, and persistence before play;
- launcher prompts for World Seed creation, environment setup, and story runtime;
- a reusable World Seed template;
- a public example World Seed, [`Old Herring’s Wake`](examples/old-herrings-wake/WORLD-SEED.md);
- the MIT License for open use, modification, and redistribution.

The Story Runtime Protocol is now available. It defines how a language model begins and resumes runs, narrates freely inside established truth, presents meaningful choices, and preserves state and history.

The initial framework package is available and has been refined with an explicit creation handoff and operational readiness gate. The World Seed creation flow has been validated with an invented public example, [`Old Herring’s Wake`](examples/old-herrings-wake/WORLD-SEED.md). The next milestone is validating the story runtime with that seed.

The repository is public so that the framework can be examined, tested, improved, and eventually used with different language models and storage environments.

## How to use False True Stories

You do not need to install an application or use a particular language model.

You need:

1. a capable language model that can read the framework documents;
2. one place to keep your private Story Pack;
3. the appropriate launcher prompt for the task you want to perform.

The public repository contains the storytelling framework. Your World Seed and Story Runs should normally be kept in a separate private location.

### 1. Choose how your story will be kept

Choose one place where the latest version of your fictional world will live.

Examples include:

- a ChatGPT Project;
- a Google Drive folder;
- another language-model project or workspace;
- a private Git repository;
- a local folder.

This location is the Story Pack’s **authoritative home** for persistent play. Avoid maintaining several independent copies that may silently drift apart.

You may instead deliberately choose **temporary-conversation mode** for a disposable story. It does not guarantee continuity beyond available conversation context. Missing storage information never selects this mode automatically.

A new Story Pack initially needs only:

```text
WORLD-SEED.md
```

When the story begins creating persistent history, it may grow into a structure such as:

```text
my-story-pack/
├── WORLD-SEED.md
└── runs/
    └── run-001/
        ├── STATE.md
        └── HISTORY.md
```

The exact filenames and folders may vary. Their responsibilities are defined in [`docs/STORY-PACK-SPECIFICATION.md`](docs/STORY-PACK-SPECIFICATION.md).

### 2. Make the framework available to the language model

Do not assume that pasting the repository URL automatically gives a language model reliable access to every file.

Depending on the service, you may:

- upload the required Markdown files;
- add them as project or workspace sources;
- make them available through a connected storage service;
- paste their contents into the session;
- clone or download the repository into an environment the model can read.

Ask the model to read the supplied files completely before it begins.

### 3. Create a new World Seed

Start a new creation session and provide these files:

- [`README.md`](README.md);
- [`docs/WORLD-SEED-GENERATION.md`](docs/WORLD-SEED-GENERATION.md);
- [`templates/WORLD-SEED-TEMPLATE.md`](templates/WORLD-SEED-TEMPLATE.md);
- [`prompts/CREATE-WORLD-SEED-LAUNCHER-PROMPT.md`](prompts/CREATE-WORLD-SEED-LAUNCHER-PROMPT.md).

Then paste or submit the contents of `CREATE-WORLD-SEED-LAUNCHER-PROMPT.md` as the instruction that begins the session.

The creation guide will ask only the questions needed to make the world playable. When the playability threshold is reached, it will declare **World Seed: Ready**, generate the complete `WORLD-SEED.md`, and stop without narration or a runtime choice.

This applies to children and simple premises too; the conversation may be shorter, but the protocol remains intact. Seed readiness describes creative playability, not persistence readiness.

For persistent play, save that generated file in the authoritative home of your Story Pack.

Do not add a private World Seed to this public framework repository unless you deliberately want to publish it as an example.

### 4. Establish the story environment

Use [Story Environment Setup](docs/STORY-ENVIRONMENT-SETUP.md) and its [launcher prompt](prompts/SETUP-STORY-ENVIRONMENT-LAUNCHER-PROMPT.md).

Provide the README, Story Pack Specification, Story Runtime Protocol, setup workflow, completed seed, and any existing setup. When resuming, also provide the selected run's latest continuity.

The guide reuses known information and asks only what remains necessary: where authority lives, how the runtime reads it, how updates are saved, who performs manual saves, which run is selected, and how private narrator material is handled when needed.

A valid existing arrangement can satisfy setup immediately. Environment definition is required for persistent play, but `ENVIRONMENT.md` is only an optional portable representation. Maintained workspace instructions or equivalent configuration can serve the same purpose.

A new run does not need empty state or history files. They are created only when the story needs continuity records.

Setup ends with the agreed arrangement and a separate runtime launch instruction. It does not tell the story.

### 5. Start a new Story Run

A clean runtime session is recommended so that unfinished creation discussion does not become accidental story truth.

Provide the runtime with:

- [`README.md`](README.md);
- [`docs/STORY-PACK-SPECIFICATION.md`](docs/STORY-PACK-SPECIFICATION.md);
- [`docs/STORY-RUNTIME-PROTOCOL.md`](docs/STORY-RUNTIME-PROTOCOL.md);
- [`prompts/START-STORY-LAUNCHER-PROMPT.md`](prompts/START-STORY-LAUNCHER-PROMPT.md);
- your completed `WORLD-SEED.md`;
- the agreed environment definition, including `ENVIRONMENT.md` if used;
- `docs/STORY-ENVIRONMENT-SETUP.md` if the arrangement may need to be established or repaired.

Then paste or submit the contents of `START-STORY-LAUNCHER-PROMPT.md` and tell the model to begin a new Story Run.

The runtime verifies creative and operational readiness before narration. If essential setup is missing, it resolves that first. Once ready, it enters the story directly, narrates freely inside established truth, offers choices only at meaningful moments, and preserves important consequences.

Submitting a seed alone does not activate runtime. A clean session is recommended; reusing a session still requires distinct runtime activation and the completed canonical seed.

### 6. Save the evolving run

The story runtime must preserve information that future sessions need.

If the language model can update files in the Story Pack’s authoritative home, allow it to maintain the selected run there.

If it cannot write to that location, the runtime supplies the agreed continuation update and the responsible saver writes it back at a natural pause. Generated updates remain pending until saved. Confirm manual saving before a new session or provider handoff; the runtime must not claim it verified an inaccessible destination.

Direct writes require successful write results. A failed saving method must be repaired or replaced before further story developments. Do not assume ordinary chat history is a permanent continuity system.

The two main run responsibilities are:

- **current state** — what is relevant and true now;
- **history** — the meaningful sequence of events, choices, discoveries, and consequences.

### 7. Resume or move an existing Story Run

Start a new runtime session or reopen an environment that can access the same Story Pack.

Provide:

- the same framework and runtime files used to start the story;
- the Story Pack’s `WORLD-SEED.md`;
- the selected run’s latest state;
- the selected run’s history;
- any other authoritative material belonging to that run;
- its current environment definition.

Submit `START-STORY-LAUNCHER-PROMPT.md` and tell the model which run to continue.

Resolve pending saves first. The runtime should reconstruct the latest saved situation and continue naturally without resetting the world or importing facts from another run.

When changing providers, load the same authoritative Story Pack and selected run, then verify the new read and saving methods. Previous provider conversation memory is not required or authoritative. Changing providers does not transfer authority; moving authority is a separate explicit decision.

### ChatGPT Project example

A practical setup is one ChatGPT Project for one private Story Pack:

1. Create a new Project for the world.
2. Add the required False True Stories framework files as project sources.
3. Start a creation chat and use `CREATE-WORLD-SEED-LAUNCHER-PROMPT.md`.
4. Save the completed `WORLD-SEED.md` back into the Project as an authoritative source.
5. Run Story Environment Setup. Confirm how current sources are read and updated; if direct updates are unavailable, designate the person who replaces the authoritative records.
6. Start a clean story chat inside the Project and use `START-STORY-LAUNCHER-PROMPT.md` after readiness passes.
7. Keep the latest saved run state and history available to later chats. If another location is authoritative, Project uploads are snapshots.

A Project is a valid authoritative home only when its current records can be maintained and made available to later sessions. Establish the actual capabilities of the chosen environment rather than assuming access or direct writes from its name.

Do not rely only on the model remembering an earlier chat. Ensure that the latest authoritative Story Pack material is available to the session that resumes the story.

### Google Drive example

Google Drive can serve as the authoritative home even when the language model itself runs elsewhere:

1. Create a private folder for the Story Pack.
2. Save `WORLD-SEED.md` in that folder.
3. Create a separate subfolder for each Story Run when continuity files become necessary.
4. Run Story Environment Setup to identify the runtime, actual access, selected run, saving responsibility, and private handling when needed.
5. In a language-model session, attach the required current files from Drive or provide accessible Drive sources if supported, then separately launch runtime.
6. At agreed pauses, save updated state and history back into the same Drive folder and resolve pending saves before resuming elsewhere.

If the chosen language model cannot read Drive directly, download the files and attach them manually.

If it can read but not write to Drive, copy its continuation update back into the authoritative files yourself.

The same pattern works with other cloud drives, local folders, private repositories, and language-model project systems:

> Make the framework readable, establish authority and persistence, launch the correct workflow, and preserve what the story makes true.

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
Story Environment Setup
      ↓
Separately launched Story Run
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

A persistent Story Pack must have one clearly identified authoritative home.

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

A reusable starting structure is available in [`templates/WORLD-SEED-TEMPLATE.md`](templates/WORLD-SEED-TEMPLATE.md).

## Story environment setup

After World Seed creation ends, [Story Environment Setup](docs/STORY-ENVIRONMENT-SETUP.md) establishes how the Story Pack is accessed, saved, and resumed. Activate it with [SETUP-STORY-ENVIRONMENT-LAUNCHER-PROMPT.md](prompts/SETUP-STORY-ENVIRONMENT-LAUNCHER-PROMPT.md).

It defines operations rather than story truth. The arrangement can be reused while valid and updated when providers, access, or authority change.

## Story runtime

Once a World Seed is complete and the environment is ready, separately launch the story runtime.

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
│   ├── STORY-RUNTIME-PROTOCOL.md
│   └── STORY-ENVIRONMENT-SETUP.md
├── prompts/
│   ├── CREATE-WORLD-SEED-LAUNCHER-PROMPT.md
│   ├── SETUP-STORY-ENVIRONMENT-LAUNCHER-PROMPT.md
│   └── START-STORY-LAUNCHER-PROMPT.md
├── templates/
│   └── WORLD-SEED-TEMPLATE.md
├── examples/
│   └── old-herrings-wake/
│       └── WORLD-SEED.md
└── LICENSE
```

The initial framework document set is now present.

The World Seed creation flow has now been validated with a single invented public example. The next step is to validate the story runtime using that seed. An example Story Run, continuity templates, or provider-specific guides should be added only when practical testing demonstrates a genuine need for them.

Files should be added when their responsibilities are understood—not merely to make the repository appear complete.

## Guiding principles

False True Stories can be summarized with a few complementary ideas:

> **False stories with their own truth.**

> **Tell the story freely. Never lie about what the world has already made true.**

> **Create enough truth to open the door. Do not build the entire forest before the listener enters it.**

These principles form the foundation of False True Stories.
