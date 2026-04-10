---
name: humanize
description: "Humanize AI-generated text to avoid AI detection. Use when the user wants to make ChatGPT, Claude, Gemini, or other AI text sound human and pass GPTZero, Turnitin, ZeroGPT, and other AI detectors."
allowed-tools: Bash(curl *)
argument-hint: "[text or file path to humanize]"
---

# AI Text Humanizer by DiaIQ

Humanize AI-generated text so it passes AI detection tools like GPTZero, ZeroGPT, Turnitin, and Copyleaks.

Powered by [DiaIQ](https://humanizer.diaiq.com) — free, no sign-up required.

## How to use

When the user asks to humanize text, call the DiaIQ humanizer API:

```bash
curl -s -X POST https://humanizer.diaiq.com/api/humanize \
  -H "Content-Type: application/json" \
  -d "{\"text\": \"TEXT_HERE\", \"passes\": 1}"
```

The API returns JSON with these fields:
- `text` — the humanized text
- `original_words` — word count of the input
- `humanized_words` — word count of the output
- `passes` — number of humanization passes applied

## Behavior

1. If the user provides text directly, humanize it.
2. If the user provides a file path, read the file first, then humanize the content.
3. Before calling the API, ask the user how many passes they want (1, 2, or 3). Explain that 1 is usually enough, but 2-3 passes produce more thoroughly rewritten text. If the user already specified passes, skip this question.
4. If the text is very long (over 2000 words), warn the user it may take a minute.
5. Show the humanized result and the word count comparison.
6. Offer to write the result to a file or copy it if the user wants.

## Important

- The API has no authentication — it's free and public.
- Do NOT send sensitive or private content without the user's explicit consent.
- The humanizer preserves meaning, facts, and structure while making text sound human.
- It works with any AI-generated text: ChatGPT, Claude, Gemini, Copilot, etc.
