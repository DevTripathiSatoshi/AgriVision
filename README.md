# Agri-Vision Platform

A mobile-first web app **UI prototype** for smallholder farmers in India, bringing crop management, livestock health tracking, disease detection, farm records, and an AI advisor into a single multilingual interface.

> **Note:** This is a front-end prototype. It demonstrates the interface and user flows with sample data. See [Project Status](#project-status) for what is and isn't functional.

---

## Preview

The app renders inside a simulated phone frame (400px wide) so it can be viewed in a desktop browser. Screens include:

- **Dashboard** — greeting, quick actions, weather, crops, livestock health, agri-news
- **AI Advisor** — a chat interface for farming questions
- **My Crops / My Livestock** — list and detail views
- **Disease Detection** — leaf analysis result screen
- **Animal Health** — health, vaccination, and treatment tabs
- **Farm Records** — income/expense tracking



## Features

- **Multilingual UI** — language switching driven by a translation dictionary (see [Language Support](#language-support))
- **Multiple screens** with a shared bottom navigation bar and slide-out side drawer
- **Tabbed detail views** for animal health records
- **Responsive card-based layout** styled to feel like a native mobile app
- **No build step** — plain HTML, CSS, and JavaScript

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Markup | HTML5 |
| Styling | CSS3 (custom, no framework) |
| Logic | Vanilla JavaScript (no dependencies) |
| Icons | Font Awesome 6.4 (CDN) |
| Fonts | Inter via Google Fonts (CDN) |

No framework, bundler, or backend is used.

---

## Project Structure

```
.
├── index.html      # All screens (shown/hidden via JS), markup, layout
├── style.css       # Full styling for the phone frame and all views
├── script.js       # Navigation, language switching, tabs, drawer logic
├── .gitattributes  # Line-ending normalization
└── assets/         # Images (see note below) — NOT included in repo
```
---

## Getting Started

### Option 1 — Open directly

Since the app is fully static, you can just open `index.html` in any modern browser.

### Option 2 — Run a local server (recommended)

A local server avoids browser quirks with local file paths:

```bash
# From the project folder:
python -m http.server 8000
```

Then visit `http://localhost:8000` in your browser.

---

## Language Support

Language is switched via the dropdown in the header. Translations live in the `translations` object in `script.js`.

| Language | Dropdown option | Status |
|----------|----------------|--------|
| English | English | ✅ Complete |
| Hindi | हिंदी | ✅ Complete |
| Punjabi | ਪੰਜਾਬੀ | ⚠️ Listed only — falls back to English |
| Marathi | मराठी | ⚠️ Listed only — falls back to English |
| Telugu | తెలుగు | ⚠️ Listed only — falls back to English |
| Tamil | தமிழ் | ⚠️ Listed only — falls back to English |

Only **English and Hindi** are actually translated. The other four appear in the dropdown but currently fall back to English, because their dictionaries aren't defined yet. To add a language, add a new key (e.g. `pa: { ... }`) to the `translations` object mirroring the English keys.

---

## Project Status

This is a **prototype / mockup**, not a production application. Being clear about this:

- **Disease detection is not real.** The "Early Blight — 92% confidence" screen shows fixed, hardcoded data. There is no image upload, model, or inference.
- **The AI Advisor is not connected to any AI.** The chat shows a scripted conversation; the input box and mic button don't send or process anything.
- **No backend or data persistence.** All figures (livestock counts, farm records, income/expense) are static text in the HTML. Nothing is saved.
- **"Add" buttons are non-functional** placeholders.

Everything present is the **user interface and navigation** — which is a legitimate and useful stage of a project, as long as it's described accurately.

---

## Roadmap

Possible next steps to move from prototype toward a working app:

- [ ] Complete Punjabi, Marathi, Telugu, and Tamil translations
- [ ] Wire up image upload + a real disease-detection model (or a third-party API)
- [ ] Connect the AI Advisor to an actual language model
- [ ] Add a backend and database for records, crops, and livestock
- [ ] Make the "Add" forms functional with persistence
- [ ] Integrate a live weather API for the user's location
- [ ] Add user authentication

---


## License

No license is currently specified. 
