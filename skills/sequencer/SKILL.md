---
name: sequencer
description: Create product ads, animate images, generate AI images, video and voiceovers, and build editable shot sequences with Sequencer. Use for Sequencer projects and generation pricing, model selection, media editing, reviews, and exports.
---

# Sequencer

Use the Sequencer MCP tools for work on the user's Sequencer account and projects.

## Connection

- Use the hosted `sequencer` MCP server supplied by this plugin.
- If authorization is required, start the Sequencer sign-in flow and let the user approve access.
- Never ask the user to paste OAuth access tokens, Firebase tokens, API keys, or device session tokens into chat.

## Workflow

1. Establish context with `list_workspaces`, `list_edits`, or another narrow read tool.
2. Before timeline changes, call `get_edit_full` so current scenes, shots, media, audio, overlays, transitions, and exports are understood together.
3. Prefer narrow mutation tools such as `update_shot`, `update_shot_media_ref`, and `update_audio_track` over broad replacements.
4. Generate or upload media before attaching its returned media ID to a shot, asset, overlay, or audio track.
5. Preserve existing work. Do not clear fields, delete records, spend credits, or export unless the user's request calls for it.
6. For subjective changes, use review tools first and apply only recommendations that match the user's intent.
7. Report the workspace, edit, and meaningful results after mutations, including IDs or output URLs that help the user continue.

## Confirmations

- Treat generation, AI editing, review exports, voice changes, and final exports as credit- or resource-consuming actions. Call them only when the user's request clearly authorizes that outcome.
- Before deleting a scene, shot, asset, media reference, transition, or audio track, identify the exact target and obtain confirmation unless the user already explicitly named that deletion.
- Never make a project public, publish media externally, or share a private project link unless the user explicitly asks.

## Reliability

- Use `get_model_catalog` to select an exact model ID and inspect supported inputs, durations, resolutions, audio options, and reference limits. Keep public model names unchanged and internal routing private.
- Before generation, call `quote_generation` with every billable setting. Show the model name, settings, USD total, timestamp, and whether the result is an estimate. Resolve missing inputs before presenting a total. Respect a budget the user already approved; otherwise ask for approval of the concrete plan and quote.
- Pass the approved `maxCostUsd` and a stable `idempotencyKey` to generation tools when supported. Reuse that key for retries of the same request, and check the returned media ID before submitting again.
- `maxCostUsd` limits each output. For multiple outputs or shots, allocate the approved total across jobs and track the remaining budget. The sum of those limits must stay within the approved total.
- Poll `get_media` until completion or a terminal error. Report the playable output URL and actual project URL returned by the tool. Link setup and discovery to `https://sequencer.media/plugin`. A queued job is still in progress.
- Treat workspace and edit IDs returned by tools as authoritative; do not invent IDs.
- Re-read affected state after multi-step changes when later steps depend on earlier writes.
- Poll asynchronous generation, workflow, review, and export operations with the matching status tool until they complete or return a clear error.
- Keep generated prompts and edit decisions aligned with the user's supplied brief and project context.
