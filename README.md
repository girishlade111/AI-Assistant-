# AI Assistant

A sleek, single-file AI chat web app powered by the **Google Gemini API** (`gemini-pro`). It gives you a polished ChatGPT-style interface in your browser — no framework, no build step, just one `index.html` file. Bring your own Gemini API key and start chatting.

## Features

- **Gemini chat interface** — conversational UI talking to `gemini-pro:generateContent`
- **Chat history** — sidebar with past conversations
- **Code rendering** — fenced code blocks with copy buttons
- **Attachments** — attach files to the chat input
- **Web search results panel** — dedicated section for search-style results
- **Modern UI** — Inter font, Font Awesome icons, responsive layout, dark aesthetic

## Tech Stack

- HTML5, CSS3 (custom, single `<style>` block)
- Vanilla JavaScript (no frameworks, no dependencies)
- Google Gemini REST API (`generativelanguage.googleapis.com`)
- Google Fonts (Inter), Font Awesome 6.4

## Quick Start

1. Clone this repo and open `index.html` in any modern browser.
2. Get a free API key from [Google AI Studio](https://aistudio.google.com/app/apikey).
3. In `index.html` (line ~1104), replace the placeholder `YOUR_API_KEY` with your key:
   ```js
   fetch('https://generativelanguage.googleapis.com/v1beta/models/gemini-pro:generateContent?key=YOUR_API_KEY', { ... })
   ```
4. Reload the page and chat away. Your key stays in your own browser.

> ⚠️ **Security note:** the key lives in client-side code. For personal use this is fine; for a public deployment, route calls through a small server-side proxy instead of shipping the raw key.

## Project Structure

```
.
├── index.html   # Entire app — markup, styles, and chat logic (~37 KB)
└── README.md
```

## Deploy Notes

Zero build required — any static host works:

- **GitHub Pages:** Settings → Pages → deploy from `main` branch, or create via the REST API (`POST /repos/{owner}/{repo}/pages` with `{"source":{"branch":"main","path":"/"}}`)
- **Cloudflare Pages / Netlify / Vercel:** drop the repo in, publish directory = repo root

## Limitations

- Single Gemini model (`gemini-pro`) — no model picker
- No streaming responses (single-shot `generateContent` calls)
- API key must be edited into the file; no key-management UI

---

Built by [Girish Lade](https://github.com/girishlade111) · [ladestack.in](https://ladestack.in)
