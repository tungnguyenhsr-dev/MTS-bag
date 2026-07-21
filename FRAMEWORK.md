# MTS Website — Framework Rules (AI Agents MUST Read)

> **CRITICAL**: This site uses **inline CSS** in `<style>` tags, NOT external files.
> `assets/mts.css` and `assets/mts.js` do NOT exist as loaded files.
> Violating these rules = broken UI. Zero tolerance.

## Stack

- **Static HTML only** — vanilla HTML/CSS/JS, no frameworks
- **CSS**: ALL inline in `<style>` tag inside `index.html`. Not a separate file.
- **JS**: ALL inline in `<script>` tags at bottom of `index.html`. Not a separate file.
- **Images**: `/images/` directory.
- **No build step**, no npm, no React/Vue/Svelte, no package.json.
- **Deploy**: Vercel auto-deploy from `master` branch.

## Design Tokens (DO NOT CHANGE)

```
--color-bg:       #F5F0EB  (cream)
--color-surface:  #FFFFFF  (card/box)
--color-ink:      #1A1A1A  (text)
--color-accent:   #C8A96E  (gold — single accent color)
--color-muted:    #6B6258  (secondary)
--color-border:   #E2D9CC
--font-sans:      'Inter', system-ui, sans-serif
--font-mono:      'JetBrains Mono', monospace
```

All CSS custom properties: colors, spacing (`--space-xs/sm/md/lg/xl/2xl`), radius (`--radius-sm/md/lg/section`), elevation (`--elevation-0/1/2/3`), motion/easing.

## New Page = Clone `index.html`

**Never build from scratch.** Always:
1. Copy `index.html`
2. Replace meta tags (title, desc, OG, canonical, keywords, JSON-LD)
3. Change nav links: `href="#section"` → `href="index.html#section"`
4. Replace content between `</nav>` and `<!-- ===== FOOTER ===== -->`
5. Keep CSS, JS, nav, footer 100% intact

## Blog Cards — Horizontal Layout

```html
<a class="blog-card" href="blog-post.html">
  <div class="blog-card-media"><img src="images/..." alt="..." loading="lazy"></div>
  <div class="blog-card-body">
    <span class="blog-card-cat"><span lang="vi">VI</span><span lang="en">EN</span></span>
    <h3 class="blog-card-title"><span lang="vi">...</span><span lang="en">...</span></h3>
    <span class="blog-card-meta">MTS · YYYY-MM-DD</span>
    <p class="blog-card-excerpt">bilingual</p>
    <span class="blog-card-link">Đọc tiếp → / Read more →</span>
  </div>
</a>
```

Available CSS: `.blog-card`, `.blog-card-media`, `.blog-card-body`, `.blog-card-cat`, `.blog-card-title`, `.blog-card-meta`, `.blog-card-excerpt`, `.blog-card-link`

## Bilingual (EN/VI Toggle)

- **All visible text** must have `<span lang="vi">` and `<span lang="en">`
- CSS: `body:not(.show-en) [lang="en"]{display:none}` / `body.show-en [lang="vi"]{display:none}`
- Nav, cards, blog content, tables, CTAs — everything needs both languages
- Test toggle after every edit

## Content CSS Classes (pre-defined)

| Class | Purpose |
|-------|---------|
| `.wrap` | Article container (760px max) |
| `.def` | Definition box (gold bg) |
| `.cta` | Call-to-action box (ink bg) |
| `p.meta` | Small date/author |
| `p.lead` | Larger intro paragraph |
| `.lang-note` | Language note at bottom |
| `.mono-label` | Section label |
| `.divider` | Section separator |
| `.lead-time-table` | Data table |

## Tables

```html
<table class="lead-time-table">
  <thead><tr><th>bilingual</th><th>...</th></tr></thead>
  <tbody>
    <tr><td>bilingual</td><td>...</td></tr>
  </tbody>
</table>
```

CSS handles alternating rows, gold hover, uppercase headers.

## Blog Post Page Requirements

- Full nav/footer from index.html template
- Back-to-blog link: `← Back to Blog` / `← Về trang Blog`
- Featured image at top (full-width, border-radius)
- Bilingual content (all text)
- JSON-LD BlogPosting schema

## Blog Post Content Required Elements

[Copied from nhaxuong content — use as workflow reference, NOT literal template]

The following checklist applies to **every blog post**:

### Front-matter / Metadata
- [ ] Title (bilingual)
- [ ] Date (Việt: "Đăng ngày ...", English: "Published ...")
- [ ] Featured image (full-width, border-radius)

### Body Structure
- [ ] Lead paragraph (bilingual, introduces the topic)
- [ ] Section headings (h2, bilingual)
- [ ] Body text (p, bilingual)
- [ ] Bullet/numbered lists where appropriate (bilingual)
- [ ] Tables where data comparison is needed (class="lead-time-table")
- [ ] Definition boxes (.def) for key concepts
- [ ] FAQ section (if applicable)
- [ ] Call-to-action box (.cta) at the bottom
- [ ] Internal links to other pages

### Tone & Positioning
- Target: brand nội địa (domestic Vietnamese brands)
- USP: thiết kế tư vấn mẫu + MOQ từ 100pcs
- NOT: tariffs, xuất khẩu, export logistics
- NOT: "bespoke", "tailoring", "couture", "made-to-measure", "B2C", "retail"

### SEO
- [ ] Unique meta title (55-65 chars)
- [ ] Unique meta description (120-160 chars)
- [ ] Canonical URL
- [ ] Open Graph tags (title, description, url)
- [ ] Twitter Card tags
- [ ] Keywords tag
- [ ] JSON-LD schema (BlogPosting or Article)

## Git

```bash
git push origin master
```

## DO NOT

- ❌ Link to `assets/mts.css` or `assets/mts.js` — CSS/JS are **inline** in the HTML
- ❌ Use inline styles when CSS classes exist
- ❌ Forget `lang="vi"` + `lang="en"` on all visible text
- ❌ Forget back-to-blog link + featured image on posts
- ❌ Modify `index.html` nav links (they use `#section` for same-page scroll)
- ❌ Push with default credential helper (times out) — use `-c credential.helper=` bypass
- ❌ Use HTML entities in string replace — file uses real Unicode (e.g. `Tùng`, not `T&ugrave;ng`)
- ❌ Forget blog content CSS classes (`.wrap`, `.def`, `.cta`) — must be added to style block
- ❌ Let AI edit HTML without reading this file first

---

*Last updated: 2026-07-21*
