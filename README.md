# 🐶🐱 Sisters of Summerville — Comic Strip Website

A dark-mode, searchable daily comic strip website featuring Honey Bear the Yorkie and Bootsie Belle the tuxedo cat. Built for GitHub Pages — free to host, easy to update daily.

🌐 **Live site:** [sisters-of-summerville.github.io/Sisters-of-Summerville](https://sisters-of-summerville.github.io/Sisters-of-Summerville/)

---

## 📁 Repository Structure

```
Sisters-of-Summerville/
├── index.html                          ← Entire website (single file)
├── captions.json                       ← All comic episode data (newest first)
├── characters.json                     ← All character profile data
├── rss.xml                             ← RSS feed for follow.it email subscribers
├── sos-banner.png                      ← Site header logo
├── David_Fliesen_with_the_Sisters_of_Summerville.JPEG  ← About page photo
├── characters/                         ← Character portrait images
│   ├── honey-bear.jpeg
│   ├── bootsie-belle.jpeg
│   └── ...
├── images/                             ← Comic strip images organized by year
│   ├── 2025/
│   │   ├── 2025-10-01.png
│   │   └── ...
│   └── 2026/
│       ├── 2026-01-01.jpeg
│       └── ...
└── README.md
```

---

## 🚀 Site Features

- **Comics** — Searchable grid of all episodes, newest first, loads 40 at a time with Load More / Load All
- **Characters** — Full character profiles with navigable detail pages
- **About** — Creator bio with photo and portfolio link
- **Subscribe** — Embedded follow.it subscription form for daily email delivery
- **Hash-based deep linking** — Every comic, character, and tab has a unique shareable URL
- **RSS feed** — `rss.xml` powers follow.it email notifications to subscribers
- **Responsive** — Works on desktop, tablet, and mobile

---

## 📅 Daily Workflow — Adding a New Episode

There are two ways to publish a new episode:

### Option A — Admin Tool (Recommended)
Use `sos-admin.html` (stored locally on your computer — never upload this to GitHub).
1. Open `sos-admin.html` in Chrome
2. Date auto-fills to today
3. Enter title, tags, and description
4. Drag and drop the comic image
5. Click **🚀 PUBLISH EPISODE**
6. The tool automatically pushes the image, updates `captions.json`, and updates `rss.xml`
7. Site goes live within ~2 minutes

### Option B — Manual Update
Update three files in GitHub:

**1. Upload the image** to the correct year folder:
```
images/2026/2026-05-01.jpeg
```

**2. Add entry to `captions.json`** (at the very top, newest first):
```json
{
  "date": "2026-05-01",
  "title": "Your Episode Title",
  "image": "images/2026/2026-05-01.jpeg",
  "tags": ["tag1", "tag2", "tag3"],
  "intro": "Your episode description here."
}
```

**3. Add entry to `rss.xml`** (just after the comment block, newest first):
```xml
<item>
  <title>Your Episode Title</title>
  <link>https://sisters-of-summerville.github.io/Sisters-of-Summerville/#2026-05-01</link>
  <description>Your episode description here.</description>
  <pubDate>Fri, 01 May 2026 12:00:00 +0000</pubDate>
  <guid>https://sisters-of-summerville.github.io/Sisters-of-Summerville/#2026-05-01</guid>
</item>
```

---

## 🔗 Shareable URLs

| Page | URL |
|------|-----|
| Homepage | `.../#` |
| Subscribe | `.../#subscribe` |
| About | `.../#about` |
| Characters grid | `.../#characters` |
| Individual character | `.../#character/honey-bear` |
| Individual comic | `.../#2026-05-01` |

Direct subscribe link: **[sisters-of-summerville.github.io/Sisters-of-Summerville/#subscribe](https://sisters-of-summerville.github.io/Sisters-of-Summerville/#subscribe)**

---

## 🖼️ Image Guidelines

- **Format**: PNG or JPEG both work
- **Size**: Square (1:1 ratio) — 1000×1000px recommended
- **Naming**: Always use the date format `YYYY-MM-DD.ext` (e.g. `2026-05-01.jpeg`)
- **Location**: Place in the correct year subfolder under `images/`
- **File size**: Compress before uploading using [squoosh.app](https://squoosh.app) — free and fast

---

## 🐾 Adding / Updating Characters

Edit `characters.json` directly in GitHub. Each entry:
```json
{
  "name": "Character Name",
  "image": "characters/character-slug.jpeg",
  "tags": ["Main Character", "Species"],
  "description": "Character bio text here."
}
```

Upload portrait images to the `characters/` folder. The URL slug is generated automatically from the name — for example `Honey Bear` becomes `#character/honey-bear`.

---

## 📡 RSS & Email Subscriptions

The site uses **follow.it** to deliver new episodes to email subscribers.

- RSS feed URL: `https://sisters-of-summerville.github.io/Sisters-of-Summerville/rss.xml`
- follow.it checks the feed periodically and emails subscribers when new items appear
- Always add new episodes to `rss.xml` as well as `captions.json` (the admin tool does both automatically)
- Never delete old items from `rss.xml` — only ever add to the top

---

## 🔍 Search

Search works automatically across episode titles, descriptions, dates, and tags. Searching always shows all matching results regardless of the current load-more pagination state.

---

## ⚠️ Important Notes

- **Never edit `index.html` by downloading from the live site URL** — Cloudflare can inject scripts into downloaded files. Always use GitHub's built-in web editor (click the pencil ✏️ icon on any file) to make edits.
- **File names are case-sensitive** on GitHub Pages — `2026-05-01.JPEG` and `2026-05-01.jpeg` are different files. Make sure the extension in `captions.json` exactly matches the uploaded file.
- **`sos-admin.html` is a local-only tool** — keep it on your computer and never upload it to this repository.

---

## 🎨 Site Colors

All colors are CSS variables at the top of `index.html`:

```css
--amber:    #f5a623;   /* Main accent — gold/amber */
--blue:     #3ab5ff;   /* Secondary accent */
--bg-deep:  #0a0808;   /* Darkest background */
--bg-card:  #1c1818;   /* Card background */
```

---

*Creative partnership between Artist + AI · Made with ❤️ for Honey Bear & Bootsie Belle · Summerville, SC*
