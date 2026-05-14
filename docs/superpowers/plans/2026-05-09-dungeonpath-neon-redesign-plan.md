# DungeonPath Neon Gaming Visual Redesign — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Redesign dungeonpath.com from plain PaperMod default to a Neon Gaming (cyberpunk) dark-themed visual style with purple/cyan gradients, custom fonts, and game-style cards.

**Architecture:** CSS-only overrides via `assets/css/custom.css` plus 2-3 Hugo template overrides using PaperMod's documented partial override system. No modifications to `themes/PaperMod/` source files.

**Tech Stack:** Hugo 0.161.1, PaperMod theme, CSS custom properties, Google Fonts (Orbitron + Inter)

---

## File Structure

| File | Action | Responsibility |
|------|--------|----------------|
| `assets/css/custom.css` | **Rewrite** | All visual override styles: CSS variables, header, footer, homepage, posts, single post, search, tags |
| `layouts/_partials/extend_head.html` | **Create** | Google Fonts preconnect + link tags for Orbitron and Inter |
| `layouts/_partials/index_profile.html` | **Create** | Custom homepage profile with Orbitron neon title, gradient buttons, no profile image |
| `layouts/_partials/footer.html` | **Create** | Restyled footer with dark background and gradient divider |
| `hugo.yaml` | **No change** | Already references `custom.css` via `params.assets.customCSS` |

---

### Task 1: Google Fonts Integration

**Files:**
- Create: `layouts/_partials/extend_head.html`

- [ ] **Step 1: Create `extend_head.html` with Google Fonts links**

This partial is injected into `<head>` by PaperMod. It loads Orbitron (for logo) and Inter (for body/headings) from Google Fonts with `font-display: swap` to avoid FOIT.

```html
{{/* Google Fonts */}}
<link rel="preconnect" href="https://fonts.googleapis.com" crossorigin>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700;900&family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
```

- [ ] **Step 2: Build and verify fonts load**

Run: `hugo server`

Open http://localhost:1313/ in browser. Verify:
- No Hugo build errors
- Fonts load (check DevTools → Network tab for Google Fonts requests)
- Page renders normally (no visible change yet since CSS isn't updated)

- [ ] **Step 3: Commit**

```bash
git add layouts/_partials/extend_head.html
git commit -m "feat: add Google Fonts for Orbitron and Inter"
```

---

### Task 2: Custom CSS — Core Variables and Global Styles

**Files:**
- Modify: `assets/css/custom.css`

- [ ] **Step 1: Rewrite `custom.css` with core variables and global styles**

This is the foundation — all CSS custom properties that override PaperMod's defaults. Grouped by: root variables, brand colors, light mode overrides, dark mode overrides, global body styles.

```css
/* ============================================================
   DungeonPath — Neon Gaming Theme
   Overrides PaperMod default styles
   ============================================================ */

/* --- Core Variables --- */
:root {
  --neon-purple: #a855f7;
  --neon-cyan: #06b6d4;
  --neon-glow: 0 0 10px rgba(168, 85, 247, 0.8), 0 0 20px rgba(168, 85, 247, 0.5), 0 0 40px rgba(168, 85, 247, 0.3);
  --gradient-brand: linear-gradient(135deg, #a855f7, #06b6d4);
  --card-glow-hover: 0 4px 20px rgba(139, 92, 246, 0.15);
  --glow-bg: radial-gradient(ellipse at top right, rgba(168, 85, 247, 0.08) 0%, transparent 70%);
  --header-bg: rgba(10, 10, 26, 0.95);
}

/* --- Dark Mode (default) --- */
:root {
  --theme: #0a0a1a;
  --entry: #111128;
  --primary: #e2e8f0;
  --secondary: #94a3b8;
  --tertiary: rgba(139, 92, 246, 0.2);
  --content: #e2e8f0;
  --border: rgba(139, 92, 246, 0.15);
  --code-bg: #0d0d1f;
  --code-block-bg: #0d0d1f;
  color-scheme: dark;
}

[data-theme="dark"] {
  --theme: #060612;
  --entry: #0d0d20;
  --primary: #e2e8f0;
  --secondary: #94a3b8;
  --tertiary: rgba(139, 92, 246, 0.25);
  --content: #e2e8f0;
  --border: rgba(139, 92, 246, 0.2);
  --code-bg: #080818;
  --code-block-bg: #080818;
  color-scheme: dark;
}

/* --- Light Mode (adjusted dark-first palette) --- */
[data-theme="light"] {
  --theme: #14142b;
  --entry: #1a1a3e;
  --primary: #e2e8f0;
  --secondary: #94a3b8;
  --tertiary: rgba(139, 92, 246, 0.2);
  --content: #e2e8f0;
  --border: rgba(139, 92, 246, 0.15);
  --code-bg: #0d0d1f;
  --code-block-bg: #0d0d1f;
  color-scheme: dark;
}

/* --- Global Background --- */
html {
  background: var(--theme);
}

body {
  background: var(--theme);
  background-image: var(--glow-bg);
  background-attachment: fixed;
}

/* --- Font Overrides --- */
body,
.entry-content,
.post-content {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}

h1, h2, h3, h4, h5, h6 {
  font-family: 'Inter', sans-serif;
  font-weight: 700;
}
```

- [ ] **Step 2: Build and verify**

Run: `hugo server`

Open http://localhost:1313/ — verify:
- Page renders in dark mode by default
- Background is dark blue-black (`#0a0a1a`), not white
- Text is light gray (`#e2e8f0`), not black
- No build errors

- [ ] **Step 3: Commit**

```bash
git add assets/css/custom.css
git commit -m "feat: add neon gaming theme CSS variables and global dark styles"
```

---

### Task 3: Custom CSS — Header and Navigation

**Files:**
- Modify: `assets/css/custom.css` (append)

- [ ] **Step 1: Append header/navigation styles to `custom.css`**

Overrides PaperMod's `header.css` styles: dark header with blur, gradient bottom border, neon logo, purple hover on nav links.

Add to end of `assets/css/custom.css`:

```css
/* ============================================================
   Header & Navigation
   ============================================================ */

/* Header background and border */
.header {
  background: var(--header-bg) !important;
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  border-bottom: 2px solid transparent;
  border-image: var(--gradient-brand);
  border-image-slice: 1;
}

/* Logo / site name */
.logo a {
  font-family: 'Orbitron', sans-serif !important;
  font-weight: 900 !important;
  font-size: 22px !important;
  color: var(--neon-purple) !important;
  text-shadow: var(--neon-glow);
  letter-spacing: 1px;
}

/* Nav links */
.menu a {
  color: var(--secondary);
  font-weight: 500;
  transition: color 0.2s ease;
  position: relative;
}

.menu a:hover {
  color: var(--neon-purple);
}

.menu a::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--gradient-brand);
  transition: width 0.2s ease;
}

.menu a:hover::after {
  width: 100%;
}

/* Active nav link */
.menu .active {
  color: var(--neon-purple) !important;
  text-decoration: none !important;
  border-bottom: none !important;
}

.menu .active::after {
  width: 100%;
}

/* Theme toggle button */
.theme-toggle {
  color: var(--secondary) !important;
}

.theme-toggle:hover {
  color: var(--neon-purple) !important;
}
```

- [ ] **Step 2: Build and verify**

Run: `hugo server`

Open http://localhost:1313/ — verify:
- Header has dark background with subtle blur
- Site name "DungeonPath" uses Orbitron font with purple glow
- Nav links turn purple on hover with sliding underline
- Active page link is purple with full underline
- Theme toggle button turns purple on hover

- [ ] **Step 3: Commit**

```bash
git add assets/css/custom.css
git commit -m "feat: add neon header styles with gradient border and glow logo"
```

---

### Task 4: Custom Homepage Profile Template

**Files:**
- Create: `layouts/_partials/index_profile.html`

- [ ] **Step 1: Create custom `index_profile.html`**

This overrides PaperMod's default profile layout. Removes the profile image (since `imageUrl` is empty), replaces title with Orbitron neon gradient text, styles buttons with gradient background.

```html
<div class="profile neon-profile">
    {{- with site.Params.profileMode }}
    <div class="profile_inner">
        {{- /* Profile image removed — no logo asset yet */ -}}
        <h1 class="neon-title">{{ .title | default site.Title | markdownify }}</h1>
        <span class="neon-subtitle">{{ .subtitle | markdownify }}</span>
        {{- partial "social_icons.html" . -}}

        {{- with .buttons }}
        <div class="buttons neon-buttons">
            {{- range . }}
            <a class="button neon-button" href="{{ trim .url " " }}" rel="noopener" title="{{ .name }}">
                <span class="button-inner">
                    {{ .name }}
                </span>
            </a>
            {{- end }}
        </div>
        {{- end }}
        <div class="neon-divider"></div>
    </div>
    {{- end}}
</div>
```

- [ ] **Step 2: Build and verify**

Run: `hugo server`

Open http://localhost:1313/ — verify:
- Homepage shows "DungeonPath" in large Orbitron font (no profile image)
- Title has gradient text effect (purple → cyan)
- Subtitle is readable below
- Buttons exist with gradient style (will look plain until CSS in Task 5)
- No build errors

- [ ] **Step 3: Commit**

```bash
git add layouts/_partials/index_profile.html
git commit -m "feat: add custom homepage profile with neon title"
```

---

### Task 5: Custom CSS — Homepage Profile Styles

**Files:**
- Modify: `assets/css/custom.css` (append)

- [ ] **Step 1: Append homepage profile styles to `custom.css`**

Styles for the `.neon-profile` class from Task 4's template.

```css
/* ============================================================
   Homepage Profile
   ============================================================ */

.neon-profile .profile_inner {
  gap: 1.2rem;
}

.neon-title {
  font-family: 'Orbitron', sans-serif !important;
  font-weight: 900 !important;
  font-size: 42px !important;
  background: var(--gradient-brand);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  margin: 0;
  letter-spacing: 2px;
  line-height: 1.2;
}

.neon-subtitle {
  font-size: 16px !important;
  color: var(--secondary) !important;
  max-width: 500px;
  line-height: 1.6;
}

.neon-buttons {
  gap: 1rem !important;
}

.neon-button {
  background: var(--gradient-brand) !important;
  color: #fff !important;
  font-weight: 700 !important;
  border-radius: 10px !important;
  padding: 0.6rem 1.5rem !important;
  font-size: 14px !important;
  border: none !important;
  transition: transform 0.2s ease, box-shadow 0.2s ease !important;
  text-decoration: none;
}

.neon-button:hover {
  transform: translateY(-2px);
  box-shadow: var(--card-glow-hover);
}

.neon-divider {
  width: 80px;
  height: 3px;
  background: var(--gradient-brand);
  border-radius: 2px;
  margin: 1rem auto 0;
}
```

- [ ] **Step 2: Build and verify**

Run: `hugo server`

Open http://localhost:1313/ — verify:
- "DungeonPath" title shows purple→cyan gradient
- "Browse Guides" and "About" buttons have gradient background
- Buttons lift up and glow on hover
- Small gradient divider line below buttons
- Mobile layout still works (buttons stack)

- [ ] **Step 3: Commit**

```bash
git add assets/css/custom.css
git commit -m "feat: add neon homepage profile styles with gradient title and buttons"
```

---

### Task 6: Custom CSS — Posts List and Cards

**Files:**
- Modify: `assets/css/custom.css` (append)

- [ ] **Step 1: Append posts list / card styles to `custom.css`**

Overrides `.post-entry` from PaperMod's `post-entry.css`: dark cards, gradient border on hover, purple title on hover, tag pill badges.

```css
/* ============================================================
   Posts List & Cards
   ============================================================ */

/* Card base style */
.post-entry {
  background: var(--entry) !important;
  border: 1px solid var(--border) !important;
  border-radius: 12px !important;
  transition: transform 0.25s ease, box-shadow 0.25s ease, border-color 0.25s ease !important;
}

.post-entry:hover {
  transform: translateY(-3px);
  box-shadow: var(--card-glow-hover);
  border-color: var(--neon-purple) !important;
}

/* Entry title */
.entry-header h2 {
  font-weight: 700;
  transition: color 0.2s ease;
}

.post-entry:hover .entry-header h2 {
  color: var(--neon-purple);
}

/* Entry footer (date, reading time, tags) */
.entry-footer {
  color: var(--secondary) !important;
}

/* Tag pills */
.post-tags a {
  background: rgba(139, 92, 246, 0.15) !important;
  border: 1px solid rgba(139, 92, 246, 0.25) !important;
  color: var(--neon-purple) !important;
  border-radius: 20px !important;
  font-size: 12px !important;
  padding: 0 12px !important;
  line-height: 28px !important;
  transition: background 0.2s ease, color 0.2s ease !important;
}

.post-tags a:hover {
  background: rgba(139, 92, 246, 0.3) !important;
  color: #e9d5ff !important;
}

/* Posts list page background */
.list {
  background: var(--theme) !important;
}
```

- [ ] **Step 2: Build and verify**

Run: `hugo server`

Open http://localhost:1313/posts/ — verify:
- Cards have dark background with subtle purple border
- Hover lifts card up, adds glow shadow, turns title purple
- Tags appear as purple pill badges
- Page background matches global dark theme

- [ ] **Step 3: Commit**

```bash
git add assets/css/custom.css
git commit -m "feat: add dark card styles with hover glow and purple tag pills"
```

---

### Task 7: Custom CSS — Single Post Page

**Files:**
- Modify: `assets/css/custom.css` (append)

- [ ] **Step 1: Append single post styles to `custom.css`**

Overrides `post-single.css` and `md-content.css` elements: headings, links, TOC, tables, blockquotes, pagination nav.

```css
/* ============================================================
   Single Post Page
   ============================================================ */

/* Post title */
.post-title {
  font-weight: 800 !important;
  color: var(--primary) !important;
}

/* Post content text */
.post-content {
  color: var(--content) !important;
}

.post-content p {
  line-height: 1.8;
  color: #cbd5e1;
}

/* Content headings */
.post-content h1,
.post-content h2,
.post-content h3,
.post-content h4,
.post-content h5,
.post-content h6 {
  color: var(--primary) !important;
}

/* Links in content */
.post-content a {
  color: var(--neon-purple);
  transition: color 0.2s ease;
}

.post-content a:hover {
  color: #c084fc;
}

/* Table of Contents */
details.toc {
  background: var(--entry) !important;
  border: 1px solid rgba(139, 92, 246, 0.2) !important;
  border-left: 3px solid var(--neon-purple) !important;
}

details.toc summary {
  color: var(--neon-purple) !important;
  font-weight: 600;
}

details.toc a {
  color: var(--secondary) !important;
}

details.toc a:hover {
  color: var(--neon-purple) !important;
}

/* Tables */
.post-content table th {
  background: var(--entry) !important;
  color: var(--primary) !important;
  font-weight: 600;
}

.post-content table td {
  color: #cbd5e1 !important;
}

/* Blockquotes */
.post-content blockquote {
  border-left: 3px solid var(--neon-purple) !important;
  background: rgba(139, 92, 246, 0.05) !important;
}

/* Tag pills on single post */
.post-tags a {
  background: rgba(139, 92, 246, 0.15) !important;
  border: 1px solid rgba(139, 92, 246, 0.25) !important;
  color: var(--neon-purple) !important;
  border-radius: 20px !important;
  font-size: 12px !important;
  padding: 0 12px !important;
  line-height: 28px !important;
  transition: background 0.2s ease, color 0.2s ease !important;
}

.post-tags a:hover {
  background: rgba(139, 92, 246, 0.3) !important;
  color: #e9d5ff !important;
}

/* Pagination nav */
.paginav {
  background: var(--entry) !important;
  border: 1px solid var(--border) !important;
}

.paginav a {
  color: var(--primary) !important;
}

.paginav .title {
  color: var(--neon-purple) !important;
}

.paginav a:hover {
  background: rgba(139, 92, 246, 0.1) !important;
}

/* Breadcrumbs */
.breadcrumbs a {
  color: var(--secondary) !important;
}

.breadcrumbs a:hover {
  color: var(--neon-purple) !important;
}

/* Post meta (date, reading time) */
.post-meta {
  color: var(--secondary) !important;
}

.post-meta a {
  color: var(--neon-purple) !important;
}
```

- [ ] **Step 2: Build and verify**

Run: `hugo server`

Open http://localhost:1313/posts/fisch/beginner-guide/ — verify:
- Title is white/light, content text is readable gray
- Links are purple, turn lighter purple on hover
- TOC has purple left border and purple summary text
- Tables have dark headers
- Blockquotes have purple left border
- Tag pills are purple
- Prev/Next pagination has dark background

- [ ] **Step 3: Commit**

```bash
git add assets/css/custom.css
git commit -m "feat: add single post page styles with neon accents"
```

---

### Task 8: Custom CSS — Search, Tags, Archives, and Footer

**Files:**
- Modify: `assets/css/custom.css` (append)

- [ ] **Step 1: Append search, tags, archives, and footer styles to `custom.css`**

```css
/* ============================================================
   Search Page
   ============================================================ */

.searchbox input {
  background: var(--entry) !important;
  border: 2px solid var(--border) !important;
  color: var(--primary) !important;
  border-radius: 10px !important;
  padding: 10px 16px !important;
  transition: border-color 0.2s ease !important;
}

.searchbox input:focus {
  border-color: var(--neon-purple) !important;
  outline: none !important;
  box-shadow: 0 0 0 3px rgba(139, 92, 246, 0.15) !important;
}

.searchResults li {
  background: var(--entry) !important;
  border: 1px solid var(--border) !important;
}

.searchResults li:hover {
  border-color: var(--neon-purple) !important;
  box-shadow: var(--card-glow-hover);
}

/* ============================================================
   Tags & Terms Pages
   ============================================================ */

.terms-tags a {
  background: rgba(139, 92, 246, 0.1) !important;
  border: 1px solid rgba(139, 92, 246, 0.2) !important;
  color: var(--neon-purple) !important;
  border-radius: 20px !important;
  padding: 8px 20px !important;
  transition: background 0.2s ease !important;
}

.terms-tags a:hover {
  background: rgba(139, 92, 246, 0.25) !important;
}

/* ============================================================
   Archives Page
   ============================================================ */

.archive-entry {
  color: var(--primary) !important;
}

.archive-entry:hover .entry-header h2 {
  color: var(--neon-purple) !important;
}

/* ============================================================
   Footer
   ============================================================ */

.footer {
  background: #060612 !important;
  color: var(--secondary) !important;
  position: relative;
}

.footer::before {
  content: '';
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 80%;
  height: 1px;
  background: var(--gradient-brand);
  opacity: 0.5;
}

.footer a {
  color: var(--neon-purple) !important;
}

.footer a:hover {
  color: #c084fc !important;
}

/* Scroll-to-top button */
.top-link {
  background: var(--entry) !important;
  border: 1px solid var(--border) !important;
}

.top-link:hover {
  color: var(--neon-purple) !important;
  box-shadow: var(--card-glow-hover);
}
```

- [ ] **Step 2: Build and verify**

Run: `hugo server`

Verify each page:
- http://localhost:1313/search/ — dark search input with purple focus border
- http://localhost:1313/tags/ — purple pill tag badges
- http://localhost:1313/archives/ — dark entries with purple hover
- http://localhost:1313/posts/fisch/beginner-guide/ — scroll to bottom, check footer has dark background and gradient divider

- [ ] **Step 3: Commit**

```bash
git add assets/css/custom.css
git commit -m "feat: add search, tags, archives, and footer neon styles"
```

---

### Task 9: Custom Footer Template

**Files:**
- Create: `layouts/_partials/footer.html`

- [ ] **Step 1: Create restyled `footer.html`**

Overrides PaperMod's `footer.html`. Keeps the same structure and Hugo/PaperMod credits but adds a neon gradient divider line. The script content (scroll-to-top, theme toggle, copy code) is kept identical to PaperMod's version.

```html
{{- if not (.Param "hideFooter") }}
<footer class="footer neon-footer">
    {{- if not site.Params.footer.hideCopyright }}
        {{- if site.Copyright }}
        <span>{{ site.Copyright | markdownify }}</span>
        {{- else }}
        <span>&copy; {{ now.Year }} <a href="{{ "" | absLangURL }}">{{ site.Title }}</a></span>
        {{- end }}
        {{- print " · "}}
    {{- end }}

    {{- with site.Params.footer.text }}
        {{ . | markdownify }}
        {{- print " · "}}
    {{- end }}

    <span>
        Powered by
        <a href="https://gohugo.io/?utm_source=papermod" rel="noopener" target="_blank">Hugo</a> &
        <a href="https://github.com/adityatelange/hugo-PaperMod/" rel="noopener" target="_blank">PaperMod</a>
    </span>
</footer>
{{- end }}

{{- if (not site.Params.disableScrollToTop) }}
<a href="#top" id="top-link" class="top-link hidden" aria-label="go to top" title="Go to Top (Alt + G)" accesskey="g">
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"
        stroke-linecap="round" stroke-linejoin="round" class="feather feather-chevrons-up">
        <polyline points="17 11 12 6 7 11"></polyline>
        <polyline points="17 18 12 13 7 18"></polyline>
    </svg>
</a>
{{- end }}

{{- partial "extend_footer.html" . }}

<script>
    let menu = document.getElementById('menu');
    if (menu) {
        const scrollPosition = localStorage.getItem("menu-scroll-position");
        if (scrollPosition) {
            menu.scrollLeft = parseInt(scrollPosition, 10);
        }
        menu.onscroll = function () {
            localStorage.setItem("menu-scroll-position", menu.scrollLeft);
        }
    }

    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener("click", function (e) {
            e.preventDefault();
            var id = this.getAttribute("href").substr(1);
            if (!window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
                document.querySelector(`[id='${decodeURIComponent(id)}']`).scrollIntoView({
                    behavior: "smooth"
                });
            } else {
                document.querySelector(`[id='${decodeURIComponent(id)}']`).scrollIntoView();
            }
            if (id === "top") {
                history.replaceState(null, null, " ");
            } else {
                history.pushState(null, null, `#${id}`);
            }
        });
    });
</script>

{{- if (not site.Params.disableScrollToTop) }}
<script>
    var toplink = document.getElementById("top-link");
    window.onscroll = function () {
        const scrollThreshold = window.innerHeight;
        if (document.body.scrollTop > scrollThreshold || document.documentElement.scrollTop > scrollThreshold) {
            toplink.classList.remove("hidden");
        } else {
            toplink.classList.add("hidden");
        }
    };
</script>
{{- end }}

{{- if (not site.Params.disableThemeToggle) }}
<script>
    document.getElementById("theme-toggle").addEventListener("click", () => {
        const html = document.querySelector("html");
        if (html.dataset.theme === "dark") {
            html.dataset.theme = 'light';
            localStorage.setItem("pref-theme", 'light');
        } else {
            html.dataset.theme = 'dark';
            localStorage.setItem("pref-theme", 'dark');
        }
    })
</script>
{{- end }}

{{- if (and (eq .Kind "page") (ne .Layout "archives") (ne .Layout "search") (.Param "ShowCodeCopyButtons")) }}
<script>
    document.querySelectorAll('pre > code').forEach((codeblock) => {
        const container = codeblock.parentNode.parentNode;
        const copybutton = document.createElement('button');
        copybutton.classList.add('copy-code');
        copybutton.innerHTML = '{{- i18n "code_copy" | default "copy" }}';

        function copyingDone() {
            copybutton.innerHTML = '{{- i18n "code_copied" | default "copied!" }}';
            setTimeout(() => {
                copybutton.innerHTML = '{{- i18n "code_copy" | default "copy" }}';
            }, 2000);
        }

        copybutton.addEventListener('click', (cb) => {
            if ('clipboard' in navigator) {
                navigator.clipboard.writeText(codeblock.textContent);
                copyingDone();
                return;
            }
            const range = document.createRange();
            range.selectNodeContents(codeblock);
            const selection = window.getSelection();
            selection.removeAllRanges();
            selection.addRange(range);
            try {
                document.execCommand('copy');
                copyingDone();
            } catch (e) { };
            selection.removeRange(range);
        });

        if (container.classList.contains("highlight")) {
            container.appendChild(copybutton);
        } else if (container.parentNode.firstChild == container) {
            // td containing LineNos
        } else if (codeblock.parentNode.parentNode.parentNode.parentNode.parentNode.nodeName == "TABLE") {
            // table containing LineNos and code
            codeblock.parentNode.parentNode.parentNode.parentNode.parentNode.appendChild(copybutton);
        } else {
            // code blocks not having highlight as parent class
            codeblock.parentNode.appendChild(copybutton);
        }
    });
</script>
{{- end }}
```

- [ ] **Step 2: Build and verify**

Run: `hugo server`

Open http://localhost:1313/ and scroll to footer — verify:
- Footer has darker background (`#060612`)
- Gradient divider line at top of footer
- Links are purple
- All scripts still work (theme toggle, scroll-to-top, copy code)
- No build errors

- [ ] **Step 3: Commit**

```bash
git add layouts/_partials/footer.html
git commit -m "feat: add restyled footer with gradient divider"
```

---

### Task 10: Final Production Build and Cleanup

**Files:**
- No new files

- [ ] **Step 1: Run production Hugo build**

```bash
hugo
```

Expected: Build completes with no errors, output in `public/` directory, ~33 pages.

- [ ] **Step 2: Verify all pages in production build**

Start production server:
```bash
npx -y serve public -l 1314
```

Open http://localhost:1314 and verify:
- `/` — Homepage: Orbitron neon title, gradient buttons, dark background
- `/posts/` — Posts list: dark cards with hover glow, purple tags
- `/posts/fisch/beginner-guide/` — Single post: readable dark theme, purple links, styled TOC
- `/posts/pressure/beginner-guide/` — Same as above
- `/about/` — About page: inherits dark theme
- `/search/` — Search: dark input, purple focus state
- `/archives/` — Archives: dark entries
- `/categories/` and `/tags/` — Term pages: purple pill badges
- Footer on all pages: dark with gradient divider
- Theme toggle works without breaking layout

Stop the server after verification.

- [ ] **Step 3: Final commit**

```bash
git add public/
git commit -m "chore: rebuild public/ with neon gaming theme"
```

---

### Task 11: Deploy to Vercel

**Files:**
- No new files

- [ ] **Step 1: Push to GitHub**

```bash
git push origin master
```

Expected: Push completes successfully. Vercel will auto-trigger a new build.

- [ ] **Step 2: Monitor Vercel build**

Check Vercel dashboard at https://vercel.com for the new deployment.

Expected: Build succeeds with Hugo, all pages render correctly on https://dungeonpath.com/

- [ ] **Step 3: Verify production site**

Check https://dungeonpath.com/ — all styles should match local Hugo build.
