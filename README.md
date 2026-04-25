# 🌹 Once Upon A Mother's Day — Developer Guide
> Sleeping Beauty–themed digital scrapbook · Built for GitHub / VS Code editing

---

## 📁 Recommended Folder Structure

```
project/
├── index.html
├── assets/
│   ├── photos/
│   │   ├── photo-1.jpg        ← Entry 1 photo
│   │   ├── photo-2.jpg        ← Entry 3 photo
│   │   ├── gallery-1.jpg      ← Entry 4 grid photo 1
│   │   ├── gallery-2.jpg      ← Entry 4 grid photo 2
│   │   ├── gallery-3.jpg      ← Entry 4 grid photo 3
│   │   ├── gallery-4.jpg      ← Entry 4 grid photo 4
│   │   └── final-photo.jpg    ← Entry 6 final photo
│   ├── videos/
│   │   ├── video-1.mp4        ← Entry 2 video
│   │   └── video-2.mp4        ← Entry 5 video message
│   ├── audio/
│   │   ├── audio-1.mp3        ← Entry 3 audio
│   │   └── final-message.mp3  ← Entry 6 voice message
│   ├── parchment-texture.png  ← (optional) background texture
│   └── paper-texture.png      ← (optional) card texture overlay
└── README.md
```

---

## 🖼️ Swapping Photo Placeholders

Find any `<div class="media-placeholder photo-placeholder">` block and **replace the entire div** with:

```html
<img class="actual-photo" src="assets/photos/photo-1.jpg" alt="Description of this photo" />
```

**For the 4-photo grid** (Entry 4), replace each grid item's `<div>` with its own `<img>` tag inside `.photo-grid`.

---

## 🎬 Swapping Video Placeholders

Find any `<div class="media-placeholder video-placeholder">` and replace with:

```html
<video class="actual-video" src="assets/videos/video-1.mp4" controls playsinline></video>
```

> Tip: Add `poster="assets/photos/video-thumb.jpg"` to show a thumbnail before play.

---

## 🎵 Swapping Audio Placeholders

Find any `<div class="media-placeholder audio-placeholder">` and replace with:

```html
<audio class="actual-audio" src="assets/audio/audio-1.mp3" controls></audio>
```

---

## 📝 Editing Text Content

Each timeline card has three editable text areas:

| CSS class      | What to change                          |
|----------------|-----------------------------------------|
| `.card-date`   | Replace `[MONTH DAY, YEAR]` with the real date |
| `.card-title`  | Chapter title (keep the Cinzel Decorative font vibe) |
| `.card-copy`   | Your personal copy/memory. Use `<em>` for italic emphasis. |

---

## ✍️ Editing the Dedication

In `.dedication-section`, replace the lorem paragraph with your own heartfelt message. Use `<strong>` for bold emphasis.

---

## 💌 Editing the Closing Signature

At the bottom of the page, find:
```html
<p class="closing-signature">With all the love in the kingdom — [Your Name]</p>
```
Replace `[Your Name]` with your actual name(s).

---

## ➕ Adding More Timeline Entries

Copy any `<article class="timeline-entry">` block and paste it before the closing `</section>`. 
- **Odd entries** (1st, 3rd, 5th…) align left on desktop
- **Even entries** (2nd, 4th, 6th…) align right on desktop
- On mobile, all entries stack in a single column automatically

Change the `data-index` attribute to the next number (e.g., `data-index="6"`).

---

## 🎨 Color Customization

All colors are CSS variables at the top of `<style>`. Key ones:

| Variable             | Default         | Use                        |
|----------------------|-----------------|----------------------------|
| `--rose`             | `#C8527A`       | Accent rose pink           |
| `--rose-deep`        | `#8B2252`       | Deep magenta / headings    |
| `--gold`             | `#D4A843`       | Gold borders & ornaments   |
| `--thorn`            | `#2D5016`       | Timeline vine line         |
| `--parchment`        | `#FAF0E0`       | Card backgrounds           |
| `--purple-maleficent`| `#4A2060`       | Book cover / intro         |

---

## 📱 Mobile Notes

- Timeline automatically switches to **single-column** on screens < 640px
- All media placeholders are responsive (fluid width, aspect-ratio locked)
- The book opening animation is sized with `min()` clamps for small screens

---

## 🚀 Deploying to GitHub Pages

1. Push the project folder to a GitHub repo
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)` folder
4. Your scrapbook will be live at `https://yourusername.github.io/repo-name/`

---

*Made with 🌹 and a little fairy magic.*
