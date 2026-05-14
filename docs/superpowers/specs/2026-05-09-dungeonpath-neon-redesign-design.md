# DungeonPath Neon Gaming Visual Redesign — Design Spec

> **Date**: 2026-05-09
> **Status**: Draft — awaiting user review
> **Goal**: Redesign dungeonpath.com from plain PaperMod default to a Neon Gaming (cyberpunk) visual style that appeals to young gamers (ages 12-25).

---

## Design Principles

- Dark-first: default to dark mode aesthetics; light mode is secondary
- Neon accent: purple-to-cyan gradient as the primary visual identity
- Minimal template changes: CSS-only overrides where possible; preserve PaperMod git submodule integrity
- Performance: no JS animations; CSS transitions only

---

## 1. Color Palette

### Light Mode (override PaperMod defaults)

| Variable | Value | Purpose |
|----------|-------|---------|
| `--theme` | `#0a0a1a` | Main background |
| `--entry` | `#111128` | Card / entry background |
| `--primary` | `#e2e8f0` | Primary text color |
| `--secondary` | `#94a3b8` | Secondary / muted text |
| `--tertiary` | `rgba(139, 92, 246, 0.2)` | Borders, subtle backgrounds |
| `--border` | `rgba(139, 92, 246, 0.15)` | Card borders |
| `--code-bg` | `#0d0d1f` | Code block background |
| `--header-bg` | `rgba(10, 10, 26, 0.95)` | Header background |

### Dark Mode (enhanced)

| Variable | Value | Purpose |
|----------|-------|---------|
| `--theme` | `#060612` | Deeper dark background |
| `--entry` | `#0d0d20` | Card background (darker) |
| `--primary` | `#e2e8f0` | Primary text |
| `--secondary` | `#94a3b8` | Muted text |
| `--tertiary` | `rgba(139, 92, 246, 0.25)` | Borders |
| `--border` | `rgba(139, 92, 246, 0.2)` | Card borders |

### Brand Colors (new variables)

| Variable | Value | Purpose |
|----------|-------|---------|
| `--neon-purple` | `#a855f7` | Primary accent |
| `--neon-cyan` | `#06b6d4` | Secondary accent |
| `--neon-glow` | `0 0 10px rgba(168, 85, 247, 0.8), 0 0 20px rgba(168, 85, 247, 0.5), 0 0 40px rgba(168, 85, 247, 0.3)` | Neon text shadow |
| `--gradient-brand` | `linear-gradient(135deg, #a855f7, #06b6d4)` | Brand gradient for titles/buttons |
| `--card-glow-hover` | `0 4px 20px rgba(139, 92, 246, 0.15)` | Card hover glow |
| `--glow-bg` | `radial-gradient(ellipse at top right, rgba(168,85,247,0.08) 0%, transparent 70%)` | Background ambient glow |

---

## 2. Typography

| Element | Font | Weight | Notes |
|---------|------|--------|-------|
| Logo (site title) | `Orbitron` (Google Fonts) | 700/900 | Only on homepage profile title |
| Headings (h1-h6) | `Inter`, sans-serif | 700/800 | PaperMod default replaced |
| Body text | `Inter`, sans-serif | 400/500 | PaperMod default |
| Code | `JetBrains Mono` | 400 | Keep PaperMod default |

**Font loading**: Add Google Fonts preconnect + `<link>` in `extend_head.html` (PaperMod partial override):
- Preconnect: `https://fonts.googleapis.com` and `https://fonts.gstatic.com`
- Font link: `Orbitron:wght@700;900` and `Inter:wght@400;500;600;700;800`
- `font-display: swap` to avoid FOIT

---

## 3. Page-by-Page Changes

### 3.1 Global (applies to all pages)

- **Body background**: `#0a0a1a` with radial gradient glow in top-right corner
- **CSS override approach**: All styles in `assets/css/custom.css` — no modifications to PaperMod theme source files

### 3.2 Header / Navigation

- Background: `rgba(10, 10, 26, 0.95)` with backdrop blur
- Bottom border: 2px purple-to-cyan gradient line
- Logo (site name): Orbitron font + neon glow text shadow
- Nav links: hover turns text purple with underline animation
- Active link: purple text + bottom border indicator

### 3.3 Homepage (Profile Mode)

Override `layouts/_partials/index_profile.html`:
- Title: Orbitron, gradient text fill (`background: var(--gradient-brand); -webkit-background-clip: text`)
- Subtitle: muted gray, slightly larger
- Buttons: gradient background (purple→cyan), white text, hover glow effect
- Remove default circular image (no logo asset yet)
- Add decorative divider line below profile section

### 3.4 Posts List (`/posts/`)

- Cards: dark background, gradient border on hover, subtle upward translate animation
- Entry title: purple accent on hover
- Tags: pill badges with purple background, cyan border variant
- Date/reading time: muted gray

### 3.5 Single Post (`single.html`)

- Keep PaperMod layout structure
- Override colors: headings use white, body uses `#e2e8f0`, links use purple
- TOC: dark background with purple accent border
- Code blocks: keep PaperMod dark style (already fits)
- Tables: dark header, gradient bottom border
- Blockquotes: left purple border, slightly lighter background

### 3.6 Footer

- Darker background (`#060612`)
- Top gradient divider line
- Muted gray text
- Remove PaperMod "Built with Hugo" link or restyle

### 3.7 About / Search / Archives / Tags

- Inherit global dark theme
- Search bar: dark input with purple focus border
- Tag list: pill badges with neon colors

---

## 4. Technical Architecture

### Files to Create

| File | Purpose |
|------|---------|
| `assets/css/custom.css` (rewrite) | All visual override styles |
| `layouts/_partials/extend_head.html` (new) | Google Fonts preconnect + link tags |
| `layouts/_partials/index_profile.html` (new) | Custom homepage profile with neon title |
| `layouts/_partials/footer.html` (new, optional) | Restyled footer |

### Files to Modify

| File | Purpose |
|------|---------|
| `hugo.yaml` | Update `customCSS` reference (already present), add `assets` config if needed |

### Files NOT to Modify

- All files under `themes/PaperMod/` — must remain untouched as git submodule
- Hugo content files (`content/posts/*.md`) — no content changes

### CSS Override Strategy

1. Override PaperMod CSS custom properties in `:root` and `[data-theme="dark"]`
2. Target specific selectors (`.post-entry`, `.header`, `.profile`, etc.) with new styles
3. Use `!important` only when PaperMod sets inline styles (should not happen)
4. Group styles by component: header, footer, homepage, posts, single post, search

---

## 5. Error Handling & Edge Cases

- **No logo image**: Profile mode currently has empty `imageUrl` — design handles this by centering title without image placeholder
- **Google Fonts not loading**: `font-display: swap` ensures fallback to system sans-serif; no layout shift beyond normal swap
- **Light mode**: User can still toggle light mode via PaperMod's theme toggle — overridden colors still apply (dark-first palette works in both modes, but light mode will have adjusted variables)
- **Mobile responsiveness**: PaperMod's existing responsive breakpoints are preserved; only colors/typography change
- **Hugo build errors**: All custom files use PaperMod's documented partial override system (`extend_head.html`, etc.)

---

## 6. Testing Plan

1. `hugo server` — verify no build errors
2. Homepage renders correctly with neon title and gradient buttons
3. `/posts/` list shows dark cards with hover glow
4. Single post page readable with adjusted colors
5. Header/nav works on mobile (responsive)
6. Theme toggle (light/dark) doesn't break layout
7. Search page renders correctly
8. Build for production: `hugo` — no errors, output in `public/`

---

## 7. Future Considerations (Out of Scope)

- Custom logo/brand image for profile mode
- Animated gradient backgrounds (CSS only, no JS)
- Custom game-specific icons or thumbnails
- Social media share cards with branded images
