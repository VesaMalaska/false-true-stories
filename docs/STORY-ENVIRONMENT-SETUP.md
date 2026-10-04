# False True Stories — Story Environment Setup

## Purpose

Establish how a Story Pack will be accessed, updated, and resumed before runtime begins.

This is operational initialization. It does not create world truth, narrate an opening, or extend the World Seed interview.

The [Story Pack Specification](STORY-PACK-SPECIFICATION.md) owns environment requirements and authority semantics. This workflow establishes the arrangement. The [Story Runtime Protocol](STORY-RUNTIME-PROTOCOL.md) verifies readiness and carries it out.

## Required inputs

Read:

- the framework `README.md`;
- `STORY-PACK-SPECIFICATION.md`;
- `STORY-RUNTIME-PROTOCOL.md`;
- this workflow;
- the completed `WORLD-SEED.md`;
- any existing environment definition;
- the selected run's current state and history when resuming.

Use authoritative material or clearly identified current snapshots. If a required source is inaccessible, request it rather than claiming to have read it.

A seed's **Ready to play** status means creative playability. It does not establish operational readiness.

## Conversational approach

Use known information first. Ask one natural, consequential question at a time; combine closely related matters only when easier for the user.

User experience is the primary design constraint. Internal rigor exists to make storytelling reliable, not to expose configuration or framework machinery. Optional preferences MUST use documented defaults when unspecified and MUST NOT block setup merely because the user did not configure them.

Do not require the user to fill in a fixed form, name technical integrations, choose whether technical files are needed, or repeat an already valid setup. A complete existing durable arrangement may need only a brief confirmation.

Explain each new responsibility when it matters. The user chooses the experience and authority; the LLM determines required records and prepares them. For persistent play, briefly explain:

> I’ll prepare a small record of where your story lives and how we save it. Once the story begins, I’ll maintain its current situation and event history. You won’t need to decide when those records are required.

Use plain language first, naming files when the user needs to recognize or save them. Later operational messages should be brief.

If the user has no preference, explain a simple workable option using an available storage method. Do not assume access, permissions, or direct writes from a provider name, project membership, or connected-service label.

For example:

> Where would you like the saved story to live? If the narrator cannot update it there, you can save its continuation updates yourself.

For a child listener, an adult or other designated saver may handle operations. The conversational style may be simpler; the protocol remains intact.

## Workflow

### 1. Identify the Story Pack and continuity mode

Identify the completed seed and whether this is a new run or an existing run.

Persistent play requires a durable authority and persistence arrangement. If that arrangement is unresolved, ask about it.

The user may deliberately select **temporary-conversation mode**. Explain that continuity beyond available conversation context is not guaranteed. Never infer temporary mode merely because storage was not mentioned.

Both modes require a playable seed, content boundaries, and a distinct run identity.

### 2. Identify authority and access

For persistent play, identify one authoritative home. A folder, repository, project, or another maintainable record system can serve this role.

Establish how the runtime gets current material:

- direct access to the authoritative home;
- current snapshots supplied by the user;
- manual download, attachment, or pasted import.

Identify snapshots as copies of that home. Uploading a copy does not transfer authority.

### 3. Agree on persistence

Determine actual write capability and permissions. Use a read-only check or reliable capability information when available; do not write merely to test setup.

Choose a workable method:

| Access arrangement | Saving method |
|---|---|
| Can read and write authority | Runtime saves selected-run updates directly and checks write results |
| Can read but cannot write authority | Runtime supplies updates; designated saver writes them back |
| Cannot access authority directly | Designated person imports current material and saves exported updates back |

Identify the responsible saver and a natural saving rhythm. Meaningful changes may be batched at scene or session pauses, but pending updates must be resolved before a new session or provider handoff.

Do not describe generated updates as saved. Manual saves require the saver to confirm completion when the runtime cannot verify the destination.

Do not create empty `STATE.md`, `HISTORY.md`, character files, or directories. Explain that runtime prepares both core continuity records at the first natural pause in the opening scene, including a listener-choice pause, or an earlier interruption, and saves them at the first agreed checkpoint. Agree on later saving points and mandatory checkpoints at session close, context-loss risk, and provider handoff. At a due checkpoint, saving must finish before further story developments.

For manual saves, provide complete replacement files by default, with clear destinations and confirmation instructions. If delivery limits require an alternative, explain the exact application steps and preserve existing content. An incomplete pair is an incomplete checkpoint.

### 4. Identify the run and required material

A new run needs a distinct identity, such as `run-001`, but not an empty folder. It begins from the seed without importing another run's events.

For an existing run, identify and load its latest saved state, history, and relevant authoritative material. Resolve pending exports or conflicting snapshots before continuation.

Make required framework and runtime inputs available. A repository URL alone does not prove that the runtime can read them.

Environment information is operational configuration. Keep it outside fictional canon. Shared settings may serve multiple runs; define how run selection and record destinations work, and identify the intended run in the handoff. Runtime rechecks selection at launch and resume. Differing access methods must remain clear. Every continuity record and export must identify its pack and run; never let shared configuration silently select or overwrite another run.

### 5. Resolve private-material handling when needed

Determine whether hidden narrator truth needs to be stored and whether the runtime can use a private channel or record.

A separate section, file, label, or warning does not provide access control by itself. Do not reveal hidden continuity in a listener-visible saving update without an agreed handling method.

If private storage is unavailable, explain the practical limitation and agree on a suitable arrangement before proceeding. Do not invent predetermined secrets merely to justify private files.

### 6. Resolve the Story Run Profile

Apply the [Story Run Profile Specification](STORY-RUN-PROFILE-SPECIFICATION.md).

For a new run, use any preferences the user has already expressed. Do not require profile configuration. If no preference is known, apply the framework defaults: balanced interaction, cinematic pacing, rich detail, open hand-offs, and always-available protagonist override.

If useful, offer customization once in plain language. Silence or indifference means use the defaults and continue.

For an existing run, reuse its saved baseline profile when available. A missing optional profile in an older pack resolves to the framework defaults; it is not a reason to block continuation.

Keep the profile as operational configuration, not fictional canon. Associate it with the selected run or a clearly defined default for new runs so changes do not leak between runs.

### 7. Record, save, and hand off the agreement

Return a concise summary covering the required environment semantics. Resolve essential unknowns before describing the setup as ready.

For newly established persistent play, the setup guide MUST prepare `ENVIRONMENT.md` and arrange its saving in the authoritative home. Do not wait for the user to request the file. Use an explicitly identified durable equivalent only when the storage system cannot use the filename. Reuse a complete existing durable equivalent rather than duplicating it. Update only missing or changed information. An agreement solely in an earlier chat must be supplied and durably recorded.

Save using the established method:

- Direct write: save the environment record and verify the successful write result.
- Manual save: provide the complete record, name its destination, and ask the responsible saver to confirm completion. Do not claim independent verification of an inaccessible destination.
- Existing record: validate its current content and durable location; save changes if required.

Use these statuses truthfully:

| Status | Meaning |
| --- | --- |
| Setup incomplete | Essential information or required sources are missing |
| Agreement complete — awaiting save | Record prepared; its persistence is not yet confirmed |
| Story Environment: Ready | Arrangement usable, required material available, and the environment record saved or a valid existing durable equivalent verified |

Temporary mode requires an explicit session agreement, playable seed, distinct run, and applicable boundaries, but no durable environment save.

The final handoff must identify:

- the agreed arrangement and selected Story Pack/run;
- the effective Story Run Profile, using plain language rather than requiring configuration syntax;
- the environment record or equivalent and its saving status;
- persistent framework sources, completed seed, environment record, and selected-run continuity needed in the story session;
- the next action: supply `START-STORY-LAUNCHER-PROMPT.md` and explicitly request a new run or continuation;
- any outstanding action preventing readiness.

Do not narrate, simulate an opening, offer a runtime choice, or automatically activate runtime. Recommend a clean runtime session; same-session reuse requires distinct runtime activation.

## Portable environment representation

`ENVIRONMENT.md` is the default required output for a new persistent arrangement. A storage limitation permits an identified durable equivalent; a complete existing durable equivalent remains compatible. The LLM handles that choice and explains it.

Use only relevant fields. This fictional example illustrates read-only access and manual saving; it makes no claim about any service's capabilities.

```markdown
# False True Stories — Environment

Continuity mode: Persistent
Story Pack: Harbour Story
Authoritative home: Private folder / Harbour Story
Runtime environment: Selected language-model workspace
Run selection: Setup handoff selects run-001; each launch/resume confirms selection.
Run records: runs/{run-id}/STATE.md and runs/{run-id}/HISTORY.md;
each record identifies Harbour Story and its run.

Read method: User supplies current attachments from the authoritative folder.
Write capability: No direct authoritative write.
Persistence method: Runtime exports state and history at natural pauses.
Responsible saver: Story creator.
Saving rhythm: First checkpoint at the opening scene's first natural pause;
then scene pauses with changed continuity, session close, and provider handoff.
Save confirmation: Creator confirms all required records saved at each due
checkpoint before further developments; no independent destination inspection.

Authority rule: Folder records are canonical; attachments are snapshots.
Required inputs: Framework specification and runtime protocol, completed seed,
latest selected-run continuity, and relevant authoritative supporting material.
Private material: Use the agreed separate narrator channel; do not export
hidden continuity into listener-visible narration.
Story Run Profile: interaction=balanced; pacing=cinematic; detail=rich;
handoff=open; protagonist override=always.
```

Do not put credentials or secrets needed for storage access in this record.

## Reconfiguration, migration, and recovery

Changing providers or workspaces does not change the authoritative home. Save pending updates, load the same selected run's latest records, and verify the new access arrangement. Previous provider memory is not a substitute for persisted continuity.

If authority itself moves, explicitly identify the new authoritative home after saving pending updates. Treat old copies as snapshots. Do not create parallel authorities or design synchronization.

An existing Story Pack without `ENVIRONMENT.md` remains compatible when a complete durable equivalent is identifiable. Reuse it or clarify only missing essentials and save the changes. If no durable equivalent exists, prepare and save the default record. Do not recreate its seed or reset its run.

If the user changes temporary play into persistent play, establish authority, save the environment record, and save recoverable state and history before further developments. Identify gaps honestly; do not manufacture missing history.

A capability change or failed persistence method requires reconfiguration before further story developments. Resolve conflicting or stale material using the authoritative records and the runtime's conflict rules.

## Completion criteria

Setup is complete when the selected pack and run are clear, required material is available, and either:

- persistent authority, access, saving responsibility, and private handling where needed are established, and the environment record is saved or a valid existing durable equivalent verified; or
- temporary-conversation mode was explicitly selected with its limitation understood.

A completed setup is permission to launch runtime separately. It is not narration and does not alter story truth.

> Establish where truth lives and how new truth reaches it.
