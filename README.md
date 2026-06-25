# Cover Letter Generator

A free, fully client-side cover letter tool for [Anuj Wadi](https://anujwadi.com). Paste a job posting, generate a tailored letter, preview it in a print-ready PDF layout, and save as PDF — all in one HTML file.

**Live file:** `cover-letter.html` — no build step, no npm, no backend.

---

## Features

- **Paste-only workflow** — copy a job description from LinkedIn, Indeed, or any site
- **Auto-detect** company, role, and job URL from pasted text
- **AI generation** via local [Ollama](https://ollama.com) (free) or optional OpenAI API key
- **Humanize pass** — extra rewrite + phrase cleanup for a more natural tone
- **Live PDF preview** — US Letter (8.5×11), centered header, justified body, your signature block
- **Print / Save as PDF** — uses `window.print()`; only the letter prints, not the UI
- **localStorage** — work survives page refresh
- **Arizona date** — automatically uses `America/Phoenix` timezone

---

## Quick start

### Option A — Open locally

```bash
cd "/path/to/this/folder"
python3 -m http.server 8765
```

Open [http://localhost:8765/cover-letter.html](http://localhost:8765/cover-letter.html)

> Use a local server (not `file://`) so Ollama API calls work.

### Option B — Host on your website

Upload `cover-letter.html` to your site root or any folder. Example:

- `https://anujwadi.com/cover-letter.html`
- or `https://anujwadi.com/cover-letter/` (rename file to `index.html`)

---

## AI setup (one time)

### Free — Ollama (recommended)

1. Install [Ollama](https://ollama.com)
2. Pull a model:
   ```bash
   ollama pull llama3.2
   ```
3. Keep Ollama running while you use the tool
4. In the app, open **AI setup** → select **Ollama** → **Test connection**

Ollama runs on your computer only. Visitors to your public website cannot use your local Ollama — this tool is best as **your personal workflow** on your own machine.

### Optional — OpenAI

1. Open **AI setup** in the app
2. Select **OpenAI**
3. Paste your API key (stored only in your browser via localStorage)
4. **Save settings** → **Test connection**

---

## How to use

1. Paste the full job posting into the text area
2. Wait ~2 seconds (auto-generate) or click **Generate cover letter now**
3. Review the preview on the right
4. Optional: add feedback → **Regenerate with feedback** or **Humanize again**
5. Click **Print / Save as PDF** and choose “Save as PDF” in the dialog

Suggested filename shown in the app:

`Cover Letter - Anuj Wadi - [Company] - [Role].pdf`

---

## Customizing the PDF layout

Everything is in `cover-letter.html`. Search for these sections:

| Section | What to edit |
|--------|----------------|
| `COVER LETTER PDF TEMPLATE STYLES` | Margins, fonts, line height, paragraph spacing |
| `COVER LETTER PDF TEMPLATE` | Name, email, phone, closing, website link |

The AI generates **4 body paragraphs** only. The template adds date, salutation, header, and signature automatically.

---

## Tech stack

- Plain HTML, CSS, JavaScript — single file
- No React, Next.js, Node, npm, database, or external CDN
- AI: Ollama (local) or OpenAI (browser fetch with your key)

---

## Privacy

- Job text and letters are saved in **your browser’s localStorage** only
- Nothing is sent to a server except your chosen AI provider (Ollama on localhost or OpenAI if configured)
- API keys are never uploaded to anujwadi.com or this repo

---

## Project structure

```
.
├── cover-letter.html   # The entire app
└── README.md           # This file
```

---

## Author

**Anuj Anil Wadi**  
[anujwadi.com](https://anujwadi.com) · awadi@asu.edu

Master's in Robotics & Autonomous Systems (AI), Arizona State University
