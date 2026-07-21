# MTS Website — Agent Rules

## ⚠️ CRITICAL: Inline CSS/JS
CSS and JS are **inline** in `<style>`/`<script>` tags inside `index.html`.
`assets/mts.css` and `assets/mts.js` do NOT exist as loaded files.
**Do NOT link to them.** They will 404.

## New Page = Clone index.html
1. Copy `index.html`
2. Replace meta + nav links (`#section` → `index.html#section`)
3. Replace content between `</nav>` and `<!-- FOOTER -->`
4. Keep CSS + JS + nav + footer intact

## Bilingual (EN/VI)
- Every visible text → `<span lang="vi">...</span><span lang="en">...</span>`
- CSS: `body.show-en [lang="vi"]{display:none}`, `body:not(.show-en) [lang="en"]{display:none}`
- Test toggle after editing

## Blog Cards
Use `.blog-card` + `.blog-card-media` + `.blog-card-body` + `.blog-card-cat` + `.blog-card-title` + `.blog-card-meta` + `.blog-card-excerpt` + `.blog-card-link`
Horizontal layout: image left (280px), content right.

## Blog Posts
- Full nav/footer from template
- `← Back to Blog` / `← Về trang Blog` link
- Featured image (full-width, border-radius)
- `.wrap` container, headings (h1→h3), `.def` boxes, `.cta` CTA, tables `.lead-time-table`
- JSON-LD schema

## Table Styling
```html
<table class="lead-time-table">
  <thead><tr><th>bilingual</th><th>bilingual</th></tr></thead>
  <tbody><tr><td>bilingual</td><td>bilingual</td></tr></tbody>
</table>
```

## Design Tokens (DO NOT CHANGE)
- Cream `#F5F0EB` bg, white `#FFF` surface, ink `#1A1A1A` text, gold `#C8A96E` accent
- Font: Inter (sans), JetBrains Mono (mono)
- Spacing: xs=8, sm=16, md=24, lg=48, xl=80, 2xl=112
- Radius: sm=8, md=12, lg=16, section=24

## Brand Positioning
- Target: **brand nội địa** (domestic Vietnamese brands)
- USP: **thiết kế tư vấn mẫu + MOQ từ 100pcs**
- NOT: tariffs, xuất khẩu, export logistics, B2C, retail, bespoke, tailoring

## GA4
ID: `G-XXXXXXXXXX` — placeholder. Replace with real ID later.

## Git Push
```bash
git push origin master
```

## DO NOT
- Add frameworks (React, Vue, Tailwind, jQuery)
- Modify index.html nav links (they use `#section` for same-page scroll)
- Remove `.reveal`, `.divider`, `.mono-label`, bilingual pairs
- Use !important or inline styles when classes exist
- Forget back-to-blog link + featured image on posts
- Forget `lang` attributes on text
