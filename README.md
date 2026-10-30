# Aristotto

Make images, videos and audio with Aristotto from Claude, ChatGPT or Codex: product photoshoots, headshots, ad cards, thumbnails, creator review videos, commercials, talking portraits, clip edits, upscales, music and narration.

## What it holds

- **The Aristotto connector**, at `https://aristotto.ai/api/mcp`. You sign in with your Aristotto account on Aristotto's own consent screen. The plugin holds no keys.
- **One skill, `aristotto`.** It routes a request to the matching recipe on Aristotto's server, which reaches your assistant over the signed-in connection.

## What it sends to Aristotto

Your request, the settings for each job, and the media you choose to use, only when you ask for a job. Every paid job is quoted first. You see its exact credit cost in a quote card, and nothing runs until you approve it there, unless you set a spending allowance for the connection on aristotto.ai. Results stay in your Aristotto library.

## Install

**Claude (web, desktop and Cowork):**

1. Open Customize, then Plugins, then Add marketplace.
2. Enter `aristotto/aristotto-plugins` and add Aristotto.
3. Connect your Aristotto account on the plugin's Connectors tab.

**Claude Code:**

```
/plugin marketplace add aristotto/aristotto-plugins
/plugin install aristotto@aristotto
```

**ChatGPT:** add Aristotto from the plugin directory.

Help: https://aristotto.ai/creative-hub/help-center · Privacy: https://aristotto.ai/privacy · Terms: https://aristotto.ai/terms
