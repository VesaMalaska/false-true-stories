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

Do not require the user to fill in a fixed form, name technical integrations, or repeat an already valid setup. A complete existing arrangement may need only a brief confirmation.

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

No empty `STATE.md`, `HISTORY.md`, character files, or directories are required. Agree how records will be saved when a continuity need arises. A complex opening may require state and history almost immediately.

### 4. Identify the run and required material

A new run needs a distinct identity, such as `run-001`, but not an empty folder. It begins from the seed without importing another run's events.

For an existing run, identify and load its latest saved state, history, and relevant authoritative material. Resolve pending exports or conflicting snapshots before continuation.

Make required framework and runtime inputs available. A repository URL alone does not prove that the runtime can read them.

Environment information is operational configuration. Keep it outside fictional canon. Shared settings may serve multiple runs; selected run identity and differing access methods must remain clear.

### 5. Resolve private-material handling when needed

Determine whether hidden narrator truth needs to be stored and whether the runtime can use a private channel or record.

A separate section, file, label, or warning does not provide access control by itself. Do not reveal hidden continuity in a listener-visible saving update without an agreed handling method.

If private storage is unavailable, explain the practical limitation and agree on a suitable arrangement before proceeding. Do not invent predetermined secrets merely to justify private files.

### 6. Record the agreement and stop

Return a concise setup summary covering the relevant environment semantics. Resolve essential unknowns before describing the setup as ready.

For persistent play, keep the definition identifiable for later sessions. Use maintained workspace instructions, equivalent configuration, or an optional portable `ENVIRONMENT.md`. Generate that file only when useful or requested.

For temporary mode, record the deliberate choice in the session; no persistence file is required.

End with **Story Environment: Ready** only when the arrangement is usable. State that the next step is a separate launch using `START-STORY-LAUNCHER-PROMPT.md` and the required runtime materials.

Do not narrate, simulate an opening, offer a runtime choice, or automatically activate runtime. Recommend a clean runtime session; same-session reuse requires distinct runtime activation.

## Optional portable representation

`ENVIRONMENT.md` is recommended when portability or manual handoffs benefit from it. It is never universally mandatory.

Use only relevant fields. This fictional example illustrates read-only access and manual saving; it makes no claim about any service's capabilities.

```markdown
# False True Stories — Environment

Continuity mode: Persistent
Story Pack: Harbour Story
Authoritative home: Private folder / Harbour Story
Runtime environment: Selected language-model workspace
Selected Story Run: run-001

Read method: User supplies current attachments from the authoritative folder.
Write capability: No direct authoritative write.
Persistence method: Runtime exports state and history at natural pauses.
Responsible saver: Story creator.
Save confirmation: Creator saves updates before another session or provider handoff.

Authority rule: Folder records are canonical; attachments are snapshots.
Required inputs: Framework specification and runtime protocol, completed seed,
latest selected-run continuity, and relevant authoritative supporting material.
Private material: Use the agreed separate narrator channel; do not export
hidden continuity into listener-visible narration.
```

Do not put credentials or secrets needed for storage access in this record.

## Reconfiguration, migration, and recovery

Changing providers or workspaces does not change the authoritative home. Save pending updates, load the same selected run's latest records, and verify the new access arrangement. Previous provider memory is not a substitute for persisted continuity.

If authority itself moves, explicitly identify the new authoritative home after saving pending updates. Treat old copies as snapshots. Do not create parallel authorities or design synchronization.

An existing Story Pack without `ENVIRONMENT.md` remains compatible. Reuse its equivalent definition or clarify only missing essentials. Do not recreate its seed or reset its run.

If the user changes temporary play into persistent play, establish authority and save recoverable state and history first. Identify gaps honestly; do not manufacture missing history.

A capability change or failed persistence method requires reconfiguration before further story developments. Resolve conflicting or stale material using the authoritative records and the runtime's conflict rules.

## Completion criteria

Setup is complete when the selected pack and run are clear, required material is available, and either:

- persistent authority, access, saving responsibility, and private handling where needed are established; or
- temporary-conversation mode was explicitly selected with its limitation understood.

A completed setup is permission to launch runtime separately. It is not narration and does not alter story truth.

> Establish where truth lives and how new truth reaches it.
