# Sequencer

Use Sequencer for product ads, image animation, AI video, image and audio generation, editable shot sequences, and generation pricing.

Select exact model IDs and supported settings with `get_model_catalog`. Call the read-only `quote_generation` tool before spending, show the USD quote and estimate status, and obtain approval unless the user has already approved that budget and plan. Resolve missing quote inputs first.

Use the approved `maxCostUsd` and a stable `idempotencyKey` where supported. Reuse the key on a retry of the same request. Poll the returned media ID through `get_media` to completion or a terminal error, then show the playable output URL. Preserve public model names and private routing. Existing project edits require reading current project state first.

`maxCostUsd` limits each output. Allocate an approved total budget across all requested outputs and shots, and track the remaining amount. Keep the sum of output limits within the approved total.

Connect using the client's Sequencer OAuth flow. Keep credentials out of chat and configuration files. Setup and starter prompts: https://sequencer.media/plugin?source=gemini-cli
