# PhotoSwipe Thumbs Plugin

A lightweight **PhotoSwipe v5** plugin that adds
 a horizontally scrollable **thumbnail strip** under the viewer.

> This repository contains the ESM plugin (`photoswipe-thumbs-plugin.esm.js`),  
> a minimal `sample.html` demo, and `package.json` ready for GitHub distribution.

---

## ✨ Features

- A nice & simple thumbnail slider
- Current thumbnail is in sync with main current image
- Zero dependency, safe for repeated init/destroy
- Fully compatible with **PhotoSwipe v5.4.4**

---

## 📂 File Structure

```
.
├── photoswipe-thumbs-plugin.esm.js
├── sample.html
├── package.json
├── README.md
└── LICENSE
```

---

## 🚀 Quick Start (no build)

1. Open `index.html` using any static server  
   (e.g. `python3 -m http.server`)
2. Ensure internet access to load PhotoSwipe from UNPKG CDN.
3. Click the arrows to see the animated looping transition.

---

## 💡 Usage (ESM)

```html
<link rel="stylesheet" href="https://unpkg.com/photoswipe@5/dist/photoswipe.css">
<div id="gallery">
  <a href="large1.jpg" data-pswp-width="1600" data-pswp-height="1067">
    <img src="small1.jpg" alt="">
  </a>
  <!-- ... -->
</div>

<script type="module">
  import PhotoSwipeLightbox from 'https://unpkg.com/photoswipe@5/dist/photoswipe-lightbox.esm.js';
  import { PhotoSwipeThumbsPlugin } from './photoswipe-thumbs-plugin.esm.js';

  const lightbox = new PhotoSwipeLightbox({
    gallery: '#gallery',
    children: 'a',
    pswpModule: () => import('https://unpkg.com/photoswipe@5/dist/photoswipe.esm.js'),
    loop: true
  });

  // Initialize plugin
  new PhotoSwipeThumbsPlugin(lightbox);

  lightbox.init();
</script>
```

---

## ⚙️ Options

| Option | Type | Default | Description |
|---|---|---|---|
| `thumbHeight` | number | `64` | Height of each thumbnail (px). |
| `thumbAspectRatio` | number | `1` | Aspect ratio (width/height) of thumbnail used to compute thumbnail width. |
| `gap` | number | `6` | Gap between thumbnails (px). |
| `paddingX` | number | `0` | Horizontal padding (left/right) inside the thumbs container (px). |
| `dragClickThreshold` | number | `6` | Pixel distance after which a drag cancels a click. |
| `autoHideOnSingle` | boolean | `true` | Do not show the thumbs UI when only one slide exists. |
| `showHideAnimationDuration` | number | `160` | Show/hide animation duration in milliseconds for the thumbs UI. |
| `scrollAnimationDuration` | number | `240` | Scroll animation duration in milliseconds for the "center active thumb" animation. |
| `classPrefix` | string | `'pswp-animated'` | CSS class prefix for injected DOM elements. |

---

## 🛠 Development

No build step is required.  
The plugin is a single **ES module** file.  
If you plan to publish to npm, update the `name`, `version`, and `exports` fields in `package.json`.

---

## 📄 License

MIT
Copyright (c) 2025 [apptaro](https://github.com/apptaro)
