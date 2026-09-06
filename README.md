# AI Business Assistant — Writer, FAQ Bot & Summarizer

A single-file, offline-friendly business assistant with three tools in one dashboard: a **Business Writer** for emails/proposals/plans, a **Customer FAQ** chatbot, and a **Text Summarizer**. Works out of the box with built-in offline templates — or connect your own OpenAI or Anthropic (Claude) API key for fully AI-generated responses.

**[View Live Demo →](#)** *(replace with your GitHub Pages demo link)*

---

## Features

- **Business Writer** — generate emails, proposals, business plan outlines, or social media posts, with a choice of tone (Formal / Friendly / Persuasive)
- **Customer FAQ Chatbot** — build a knowledge base of question/answer pairs; the assistant matches customer questions to the closest FAQ entry, or (with an API key connected) answers more open-ended questions using your FAQ entries as context
- **Text Summarizer** — paste any text and get a short or medium-length summary
- **Two modes, same interface:**
  - **Offline mode** (default, no setup): templates for the Writer, keyword matching for the FAQ bot, and a frequency-based extractive algorithm for the Summarizer — all built in, no API key required
  - **AI mode** (optional): add your own OpenAI or Anthropic API key in Settings, and all three tools call the real model directly from your browser for genuinely generated content
- **History** — every generation is logged, with a badge showing whether it came from AI or the offline templates
- **Day / Night theme** — toggle between light and dark mode
- **No backend required** — runs entirely in the browser using LocalStorage; no server, database, or account needed
- **Responsive** — works on desktop, tablet, and mobile

## Getting Started

1. Download or clone this repository
2. Open `index.html` in any modern browser
3. Start using the Assistant right away in offline mode — no setup needed
4. Optional: go to **Settings**, choose OpenAI or Anthropic, and paste in your own API key for AI-generated responses

No build step, no dependencies, no installation.

## How the AI Connection Works

When you add an API key in Settings, this app calls the official OpenAI (`api.openai.com`) or Anthropic (`api.anthropic.com`) chat endpoint **directly from your browser** using your key. No request ever passes through a server belonging to us — your key and your prompts go straight from your browser to your chosen provider, and your key is stored only in this browser's LocalStorage.

This also means:
- You are billed directly by OpenAI/Anthropic according to their own pricing for whatever you generate
- Your API key is visible in your own browser's network requests (as with any client-only AI tool) — don't share your screen or browser dev tools with anyone you don't trust while a key is saved
- If no key is set, or a request fails, the app automatically falls back to the offline templates so it still works

## Tech Stack

- HTML5, CSS3 (custom properties for theming), vanilla JavaScript
- Direct `fetch()` calls to the OpenAI and Anthropic chat APIs — no SDK or backend required
- A simple frequency-based extractive summarization algorithm for offline mode (no AI needed)
- Browser LocalStorage for data persistence
- Google Fonts (Space Grotesk, Inter, JetBrains Mono)

## Data & Privacy

All data — including your API key, if you add one — is stored locally in your browser's LocalStorage. Nothing is sent to any server of ours. Clearing your browser data will reset the app; use the **Reset Demo Data** button in the sidebar to restore the sample dataset (this also clears any saved API key).

## Important

This is a front-end, browser-based application. It does not include a hosted backend, cloud database, user authentication, or server-side sync across devices — and it does not include an AI subscription of any kind; connecting AI mode requires your own OpenAI or Anthropic account and API key.

Your data persists in the browser until you clear site data or use the Reset Demo Data button — it does **not** auto-reset on its own, so it's safe for real day-to-day use. (The separately hosted live demo does reset nightly, so visitors always see a clean sample dataset — that behavior is not present in this package.)

## License

See `LICENSE` file.

## Support

Built and maintained by UpComing Solution. For customization, bulk licensing, or a hosted/multi-user version with a real backend, get in touch.
