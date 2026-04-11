![DiaIQ Humanizer](./banner-humanizer-high-res.png)

# Humanize AI Text — Claude Code Skill

Free Claude Code skill that humanizes AI-generated text so it passes GPTZero, ZeroGPT, Turnitin, Copyleaks, and other AI detectors.

Powered by [DiaIQ Humanizer](https://humanizer.diaiq.com) — no API key, no sign-up, no cost.

## Install

```bash
npx skills add diaiq/claude-skill-humanizer
```

## Usage

Once installed, just ask Claude to humanize text naturally:

```
humanize this text: Your AI-generated content here...
```

Or use the slash command:

```
/humanize Your AI-generated content here...
```

You can also point it at a file:

```
/humanize path/to/article.md
```

## What it does

- Rewrites ChatGPT, Claude, Gemini, Copilot, or any AI-generated text to sound human
- Passes GPTZero, ZeroGPT, Turnitin, Copyleaks, and other AI content detectors
- Preserves meaning, facts, and formatting (headings, lists, markdown)
- Supports 1-3 humanization passes for deeper rewriting

## How it works

The skill calls the free [DiaIQ Humanizer API](https://humanizer.diaiq.com/api/humanize). No authentication required. Your text is sent to the API, humanized using a fine-tuned local AI model, and returned directly in your terminal.

## About DiaIQ

[DiaIQ](https://diaiq.com) converts video recordings into blog posts, newsletters, social media posts, and more. The humanizer was originally built for our own content pipeline and is now available as a free public tool.
