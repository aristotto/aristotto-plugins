---
name: aristotto
description: Make images, videos and audio with Aristotto, including product photoshoots, headshots, ad cards, thumbnails, creator review videos, commercials, talking portraits, clip edits, upscales, music and narration. Use when the user asks for any of these, names an Aristotto skill, or types /aristotto with a request.
---

# Aristotto

Route the request through the connected Aristotto tools. The recipes for each kind of job live on Aristotto's server and reach you over the signed-in connection, so keep no list of your own of skills, models, inputs or credit costs.

## Connect first

If the Aristotto tools aren't available, ask the user to connect their Aristotto account to this plugin, then stop.

## Route the request

1. Call `list_workflows`. If the user named a skill, for example "product photoshoot" or `/aristotto talking-portrait`, use that skill. Otherwise pick the skill whose description fits the request. If none fits, use `aristotto-creative-production` alone.
2. Call `read_workflow_file` for `aristotto-creative-production`, then for the chosen skill, and follow both files.
3. Keep the user's brief, references, chosen model, format and count. Ask only what the recipe needs and the conversation hasn't answered.

## Media

- Use media from the user's Aristotto library with `list_uploads`.
- Import an image attached in this chat with `import_chat_image`, or a public link the user gives with `import_media_url`.
- Otherwise open `show_upload_picker` so the user can add files from their device.
- Use only media the user owns or gave for this task.

## Quote and approve

- Every paid job is quoted first, with its exact credit cost. Use the quote tool the connection lists, as the recipe and the server instructions say.
- The user approves in the quote card, or at the quote's review link when no card shows. A quote that fits a spending allowance the user set for this connection on aristotto.ai starts at once; say so.
- Never start a job from the conversation, and never treat the user's chat reply as approval.
- If the user changes a pending proposal, quote again and name the pending quote it replaces. If the user declines, call `reject_quote`.
- Read the balance with `get_balance` when the user asks how many credits they have.

## Deliver the result

- Follow each job until it is completed, failed or cancelled. Where a result card shows, let it update. Where none shows, use `get_job`, or `wait_for_jobs` for several jobs.
- Say a job is done only when it reports completed, and say plainly when one failed and whether its credits came back.
