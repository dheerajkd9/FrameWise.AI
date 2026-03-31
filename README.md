# FrameWise — AI Wedding Album Curator

> **Privacy-first, zero-storage AI curation for wedding photos.**
> Your photos never leave your Google account.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-framewise.app-rose)](https://your-username.github.io/framewise)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## What is FrameWise?

FrameWise is a static, single-file web app that helps couples automatically curate their wedding photos into four beautiful albums — using Google's Gemini AI — **without ever uploading their photos to a third-party server.**

Instead of storing your photos, FrameWise generates a personalised **Google Apps Script** that runs entirely inside your own Google account. You paste it into Google's free script editor, press Run, and wake up to your curated albums in Google Drive.

---

## Four Albums, One Run

| Album | What it finds | Best for |
|---|---|---|
| 💍 **Best Of** | Sharp, emotional, print-worthy moments | Wedding album / photographer |
| 🤣 **Candids** | Unposed, spontaneous, real moments | Share with family |
| ✨ **Décor & Details** | Flowers, henna, venue, jewellery | Instagram / social |
| 🎲 **Hidden Gems** | Weird, random, aww background moments | The secret album |

---

## How It Works

```
User fills in form → FrameWise generates script (in browser) →
User pastes script into script.google.com →
Script runs in user's Google account →
Gemini AI scores every photo →
Albums appear in user's Google Drive
```

**Nothing is ever sent to FrameWise servers.** The script generator runs entirely client-side in the browser.

---

## Features

- ✅ **Zero data storage** — photos stay in your Google Drive
- ✅ **Multi-album generation** — 4 album types in one overnight run
- ✅ **Custom AI prompts** — describe moments you want found (e.g. "capture every photo with grandparents")
- ✅ **Candid theme engine** — find background aww moments, random gems, weird stuff
- ✅ **Progress saving** — resumes after every photo, never loses work on timeout
- ✅ **Single file** — entire app is one HTML file, no build step, no dependencies
- ✅ **Free to run** — uses Google's $300 free cloud credits (~₹50–400 for 700 photos)

---

## Getting Started (for users)

1. **Open the app** at [your deployed URL]
2. Fill in your Google Drive folder URL and Gemini API key
3. Select your album types, add your wedding events, write custom AI themes
4. Copy the generated script
5. Paste into [script.google.com](https://script.google.com) → New Project
6. Run `startFresh` and go to sleep
7. Wake up to your albums in Google Drive ☀️

### Getting a Gemini API Key (free)

1. Go to [aistudio.google.com](https://aistudio.google.com)
2. Click **Get API Key → Create API Key**
3. For privacy + no rate limit errors, enable billing at [cloud.google.com/free](https://cloud.google.com/free) (free $300 credits, no charge)

---

## Deploying FrameWise

Since it's a single HTML file, deployment is trivial:

### GitHub Pages (free)
```bash
git clone https://github.com/YOUR_USERNAME/framewise
cd framewise
# drop wedding_curator.html in as index.html
git add .
git commit -m "deploy"
git push origin main
# Enable Pages in repo Settings → Pages → main branch
```

### Netlify / Vercel (free)
Just drag and drop `wedding_curator.html` into the Netlify drop zone at [app.netlify.com/drop](https://app.netlify.com/drop). Live in 30 seconds.

---

## Project Structure

```
framewise/
├── index.html        # Entire app — self-contained, no dependencies
└── README.md
```

No `package.json`. No build step. No node_modules. Just open `index.html` in a browser.

---

## Privacy Architecture

```
┌─────────────────────────────────────────────────────┐
│                  USER'S BROWSER                      │
│  FrameWise form → generates script locally           │
│  No data sent to FrameWise servers                   │
└─────────────────────────┬───────────────────────────┘
                          │  User copies script
                          ▼
┌─────────────────────────────────────────────────────┐
│              USER'S GOOGLE ACCOUNT                   │
│  Google Apps Script reads photos from Drive          │
│  Sends photos to Gemini API (Google's servers)       │
│  Writes curated albums back to Drive                 │
└─────────────────────────────────────────────────────┘
```

> **Recommendation:** Use the paid Gemini API (enabled via Google Cloud billing) so Google does not use your photos for AI model training. The paid tier costs ~₹50–400 total for a typical wedding — not per month.

---

## Customising the AI

In the app's **AI Themes** step, you can write plain-English instructions:

**Custom moments to prioritise:**
```
Capture every photo where the couple is looking at each other.
Prioritise any photo with grandparents or elderly family members.
Score outdoor natural-light shots higher than indoor flash photos.
```

**Things to avoid:**
```
Avoid near-duplicate burst shots.
Skip photos where catering staff are the main subject.
```

**Candid & Hidden Gem themes:**
```
Find any child doing something cute or unexpected.
Look for guests who are crying happy tears.
The flower girl looking bored or distracted — definitely include.
```

---

## Roadmap

- [ ] Video highlight reel support (Gemini video API)
- [ ] Direct Google Photos album creation
- [ ] WhatsApp-optimised compressed export
- [ ] Multi-language support
- [ ] Photographer portal (bulk processing multiple weddings)

---

## Built With

- Vanilla HTML/CSS/JS — zero dependencies
- [Google Apps Script](https://script.google.com) — runs inside user's Google account
- [Gemini API](https://aistudio.google.com) — AI photo scoring
- [Google Drive API](https://developers.google.com/drive) — photo access and album creation

---

## License

MIT © FrameWise

---

*Built with ❤️ for privacy-conscious couples everywhere.*
