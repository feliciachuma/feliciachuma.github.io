# Felicia Chuma &mdash; Personal Portfolio & Blog

Personal portfolio and technical writing space of **Felicia Chuma**, an IT support graduate studying for a **Bachelor of Commerce in Data Science and Informatics** at Midlands State University, Zimbabwe, and President of the MSU chapter of Data Science Zimbabwe.

The site is built with pure web fundamentals: **semantic HTML5, modern CSS, and vanilla JavaScript**. It requires no framework, no runtime dependencies, no bundler, and no Node.js/npm toolchain. All pages are generated via a lightweight, standard-library Python 3 builder.

---

## Flagship Project: Vision-SL

**Vision-SL** is an offline, privacy-preserving computer-vision platform for teaching, practising and translating Zimbabwe Sign Language (ZSL).

- **The Challenge**: Zimbabwe recognizes sign language in its Constitution, but structured teaching tools and certified interpreters remain scarce outside major cities. High internet data costs prevent access to cloud-only solutions, and streaming classroom video of children raises serious privacy concerns.
- **The Solution**: Operates entirely offline on local networks. Hand tracking runs client-side using MediaPipe, processing only 21-point coordinate landmarks so video never leaves the device. Offers interactive practice with real-time scored feedback and continuous fingerspelling-to-text translation.
- **Inclusive Tech Mission**: Proving that cutting-edge computer vision and accessible technology can run on low-cost, offline hardware to solve real community needs in Zimbabwe.

---

## Tech Stack & Architecture

- **Front End**: Pure HTML5, CSS3 (design tokens, progressive animations, dark palette: *Midnight Intelligence*), and vanilla ES5 JavaScript.
- **Generator**: Single-script Python 3 engine (`_tools/build.py`) using standard library only.
- **Hosting**: GitHub Pages (`feliciachuma.github.io`).
- **SEO & Accessibility**: Complete Open Graph / Twitter Cards, JSON-LD structured data (`Person`, `WebSite`, `Blog`), responsive WebP/JPEG pictures, skip link, and strict heading hierarchies.

---

## Repository Structure

```
_content/
  content.json            # Single source of truth for text, lists, and metadata
  blog/                   # Markdown articles and draft templates
_tools/
  build.py                # Static site generator (Python 3 stdlib)
  optimise-image.py       # Image optimizer for WebP & progressive JPEG (Pillow)
css/
  site.css                # Global stylesheet and design tokens
js/
  site.js                 # UI enhancements (nav, reveal-on-scroll, progress bar)
  blog.js                 # Blog filtering and interactions
assets/
  images/                 # Optimized responsive images
  icons/                  # SVG icons and favicon
index.html, blogs/, ...   # Generated output (committed for GitHub Pages)
```

---

## Getting Started

### 1. Build and configure site metadata

Run the builder to regenerate all static HTML, feeds, and sitemaps:

```bash
# Basic rebuild
python3 _tools/build.py

# Set personal metadata flags (saves directly back to _content/content.json)
python3 _tools/build.py \
  --url https://feliciachuma.github.io \
  --email you@example.com \
  --linkedin https://www.linkedin.com/in/your-profile \
  --github https://github.com/your-username \
  --form-endpoint https://formspree.io/f/xxxxxxxx
```

> **Note**: Use `--url` (not `--site-url`) to configure your canonical website address.

### 2. Preview locally

Start a local HTTP server:

```bash
python3 -m http.server 8000
```

Open [http://localhost:8000](http://localhost:8000) in your browser.

### 3. Deploy changes to GitHub Pages

Always regenerate the site and push both sources and output:

```bash
# 1. Regenerate
python3 _tools/build.py

# 2. Stage changes
git add .

# 3. Commit
git commit -m "Deploy: update portfolio content and layout"

# 4. Push to publish live
git push origin main
```

---

## Content Updates

- **Portfolio text & lists**: Edit `_content/content.json` and run `python3 _tools/build.py`. Never hand-edit `index.html` or generated files directly.
- **Publishing a blog post**: Copy `_content/blog/_post-template.md` to `_content/blog/<slug>.md`, fill in front matter, write your post, and rebuild.
- **Optimizing images**: Run `python3 _tools/optimise-image.py path/to/image.jpg short-name` to produce responsive WebP and JPEG assets in `assets/images/`.

---

## License & Copyright

&copy; 2026 Felicia Chuma. All rights reserved.
