# 🐶🐱 Sisters of Summerville — Comic Strip Website

A dark-mode, searchable comic strip website. Built for GitHub Pages — free to host, easy to update.

---

## 📁 Folder Structure

```
sisters-of-summerville/
├── index.html          ← The entire site (single file)
├── images/
│   ├── ep001.png       ← Episode 1 image
│   ├── ep002.png       ← Episode 2 image
│   ├── ep007.png       ← etc.
│   └── ...
└── README.md
```

---

## 🚀 Deploying to GitHub Pages (Free!)

### First time setup:
1. Create a free account at [github.com](https://github.com) if you don't have one
2. Click **New Repository** → name it `sisters-of-summerville` (or `yourusername.github.io` for a root portfolio site)
3. Upload all your files (drag & drop works in the GitHub web UI)
4. Go to **Settings → Pages → Source → Deploy from branch → main → / (root)**
5. Your site will be live at: `https://yourusername.github.io/sisters-of-summerville`

### After first setup — adding a new episode:
1. Open `index.html` in any text editor (VS Code recommended)
2. Find the `const COMICS = [` section near the bottom
3. Add your new episode as the FIRST item in the array (newest first):

```javascript
{
  ep: "Ep. 8",
  date: "March 21, 2025",
  title: "Your Episode Title",
  image: "images/ep008.png",
  tags: ["tag1", "tag2", "tag3"],
  intro: `Your episode description here.

You can use blank lines for paragraphs.
Multi-line text is supported naturally.`
},
```

4. Drop your new `ep008.png` into the `images/` folder
5. Commit and push — site updates automatically!

---

## 🖼️ Image Tips

- **Format**: PNG or JPG both work fine
- **Size**: Square images (1:1 ratio) look best — e.g. 1000×1000px
- **File size**: Compress images before uploading (use [squoosh.app](https://squoosh.app) — free, drag & drop)
- **Naming convention**: `ep001.png`, `ep002.png`, etc. keeps things tidy

---

## 🔍 Search

Search works automatically across:
- Episode titles
- Episode intro text
- Tags
- Episode numbers

---

## 📬 Newsletter Integration

The newsletter signup is currently a placeholder. To wire it up:

### Option A — Mailchimp (free up to 500 subscribers)
1. Create a Mailchimp account → Audience → Signup forms → Embedded forms
2. Copy your form action URL
3. In `index.html`, find `handleNewsletterSubmit()` and replace with a real POST to your Mailchimp URL

### Option B — ConvertKit / Beehiiv
Similar process — both have free tiers and good embed options.

---

## 📱 Social Share

Each episode has:
- Facebook share button
- X (Twitter) share button  
- Copy link button
- Native share on mobile (uses device share sheet)

---

## 🎨 Customizing

All colors are CSS variables at the top of `index.html`:

```css
--amber:      #f5a623;   /* Main accent color */
--blue-glow:  #3ab5ff;   /* Secondary accent */
--pink:       #e85fa0;   /* Tertiary accent */
--bg-deep:    #0e0c10;   /* Darkest background */
--bg-card:    #1e1a26;   /* Card background */
```

Change `--amber` to change the whole site's accent color instantly.

---

## 🔗 Linking from Facebook

Your Facebook bio/posts can link directly to:
- `https://yourusername.github.io/sisters-of-summerville` — homepage
- Add `#Ep7` to deep-link to specific episodes (optional enhancement)

---

## 📂 Back-filling 6 Months of Episodes

To add all your back issues at once:
1. Collect all your comic images — name them `ep001.png` through `ep180.png` (or however many)
2. Build out the COMICS array in `index.html` with all entries
3. Push everything at once

A good workflow: keep a spreadsheet of episode #, date, title, intro text → paste into the JS array in one session.

---

*Made with ❤️ for Honey Bear & Bootsie Belle · Summerville, SC*
