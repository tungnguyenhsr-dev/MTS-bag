# MTS Website — Framework Rules for AI Coding Agents

> **READ THIS BEFORE EDITING ANY FILE.**
> Violating these rules = broken site. Zero tolerance.

---

## 1. Stack — Static HTML Only

- **No framework.** Pure vanilla HTML + CSS + JS.
- **No build step.** No npm, no webpack, no React/Vue/Svelte.
- **No backend.** Static files served via Vercel/GitHub Pages.
- **Do NOT add** any package.json, bundler, framework, or dependency.
- **Do NOT change** file extensions (.html → .jsx, etc.).

## 2. Design Tokens (RO — Read Only)

Defined in `assets/mts.css` `:root`. Never change these values:

```
--color-bg:       #F5F0EB    (cream)
--color-surface:  #FFFFFF    (card)
--color-ink:      #1A1A1A    (text)
--color-accent:   #C8A96E    (gold — single accent color)
--color-muted:    #6B6258    (secondary text)
--section-dark:   #1A1A1A    (dark section bg)
--color-on-dark:  #FFFFFF    (text on dark)

--font-sans:      'Inter', system-ui, sans-serif
--font-mono:      'JetBrains Mono', ui-monospace, monospace
```

**Do NOT:**
- Add new colors / brand colors.
- Change existing color values.
- Add CSS frameworks (Tailwind, Bootstrap).

## 3. File Structure

```
index.html                  ← Homepage (single page app — all content here)
blog.html                   ← Blog listing
blog-oem-bag-vietnam.html   ← Blog post 1
blog-start-bag-brand.html   ← Blog post 2
assets/
  mts.css                   ← ALL styles (single file, ~780 lines)
  mts.js                    ← JS (theme toggle, language toggle, nav)
  favicon.svg
  mts-logo-dark.svg
  mts-logo-light.svg
images/                     ← Product & factory images (10+ PNG files)
```

**Do NOT:**
- Split CSS into multiple files.
- Create new .js files unless absolutely necessary.
- Delete or rename existing assets.

## 4. HTML Structure Rules

### Sections (in order)
```
NAV (#hero sticky nav)
HERO (#hero)
TRUST STRIP (#trust)
CAPABILITIES (#capabilities)
SERVICES (#services)
PRODUCTS (#products, optional)
QC (#quality)
BLOG (#blog — latest articles, optional)
CTA (#cta)
CONTACT (#contact)
FOOTER (#footer)
```

### Built-in Patterns
- **Bilingual:** Every content block has `<tag lang="vi">` + `<tag lang="en">`. JS `#langToggle` shows/hides based on active language.
- **Dark sections:** hero, trust strip, cta, blog hero use `background: var(--section-dark); color: var(--color-on-dark);`
- **Reveal animation:** Key sections have `class="section-inner reveal"`. JS `.reveal` is already handled — don't remove or replace.
- **Mono labels:** Each section starts with `<span class="mono-label">XX — NAME</span>`.
- **Horizontal divider:** `<hr class="divider">` separates major sections.
- **Buttons:** `.btn-primary` (gold bg + ink text), `.btn-secondary` (outline).

### Do NOT
- Remove `<hr class="divider">` between sections.
- Remove `class="reveal"` from section wrappers.
- Merge or delete section IDs.
- Change section ordering.
- Remove bilingual structure (VI/EN pairs).

## 5. CSS Rules

- All styles in `assets/mts.css` (~780 lines, single file).
- Uses CSS custom properties (design tokens) — do NOT hardcode colors/fonts.
- BEM-like naming but not strict — match existing patterns.
- Radius: inner 8px, interactive 12px, container/card 16px, section 32px.
- Elevation: 1px border for default, subtle shadow for cards.

**Do NOT:**
- Use !important.
- Add inline styles in HTML.
- Add new CSS files.
- Override design tokens.

## 6. JS Rules

- All JS in `assets/mts.js`.
- Features: theme toggle (🌙/☀️), language toggle (VI/EN), mobile nav hamburger, .reveal intersection observer, smooth scroll.
- **Do NOT** add jQuery, Alpine.js, or any JS library.
- **Do NOT** remove existing JS functionality.

## 7. Content Editing Rules

When editing content:
1. **KEEP the HTML structure intact.** Only change text inside `<p>`, `<h1>`, `<h2>`, `<span>`, `<div>` — do NOT change classes or nesting.
2. **Maintain bilingual pairs.** Every VI block has an EN counterpart.
3. **Brand positioning:** OEM bag/backpack manufacturer, B2B only, Vietnam-based. Forbidden: "bespoke", "tailoring", "couture", "made-to-measure", "retail", "B2C".
4. **GA4 ID:** `G-XXXXXXXXXX` — placeholder. Replace only with real Measurement ID from Tommy.
5. **Images:** `images/*.png` are product/factory photos. Do NOT delete references even if image is placeholder.

## 8. Git Rules

- Only push to `master` branch.
- Commit messages: `type: scope — description` (e.g. `feat: blog — add OEM guide post`).
- **No force push.**
- Verify site renders locally before committing.

---

*Generated 2026-07-21. Last updated by Hermes Agent.*
