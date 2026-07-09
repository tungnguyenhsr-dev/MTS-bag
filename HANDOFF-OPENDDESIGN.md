# HANDOFF — MTS Website → OpenDesign (UI Fix)

**Repo:** github.com/tungnguyenhsr-netizen/MTS-bag
**File chính:** `index.html` (single static HTML, inline CSS + 1 script)
**Deploy:** Vercel auto-build từ `master` → mts-bag.vercel.app
**Last good commit:** `330aa13`

---

## 1. BRAND / TASTE CONSTRAINTS (phải giữ)
- Palette CHỈ 3 màu: `#1A1A1A` (ink black) / `#C8A96E` (warm gold, single accent) / `#F5F0EB` (cream bg).
- Mono section labels (JetBrains Mono), uppercase, format `05 — NHÀ MÁY / FACILITY`.
- Editorial B&W + gold, asymmetric, tight spacing, 1px dividers. KHÔNG shadow nặng (dùng border/elevation token).
- CTA chuẩn: "Bắt Đầu Dự Án →" (VI) / "Start Your Project →" (EN), song ngữ.
- Cấm từ: bespoke / tailoring / couture / made-to-measure.
- Font: Inter (body) + JetBrains Mono (labels).

## 2. DESIGN TOKEN SYSTEM (Astryx-style, đã áp dụng)
Định nghĩa trong `:root` đầu file. Dùng token, không hardcode:
- Color: `--color-bg/--color-surface/--color-ink/--color-accent/--color-muted/--color-border`
- Space: `--space-xs..2xl` (8px base)
- Radius: `--radius-sm/md/lg`
- Motion: `--motion-fast/base/slow`, `--ease-standard/out`
- Elevation: `--elevation-0/1` (border-based)
- Legacy aliases (`--primary/--gold/--accent`) vẫn map sang token để rule cũ chạy.

## 3. KNOWN UI BUGS CẦN FIX (priority)
### 🔴 BUG A — Reveal animation làm mất nội dung (critical)
- `.reveal{opacity:0;transform:translateY(28px)}` ẩn mọi section cho tới khi JS thêm `.in-view`.
- Nếu tool render không chạy JS (OpenDesign preview, NoScript, SSR), **toàn bộ trang trắng/ẩn**.
- **Fix:** đổi thành safe fallback — `.reveal{opacity:1}` mặc định, chỉ ẩn khi JS đã bật (thêm class `js` vào `<html>` qua script, rồi `.js .reveal{opacity:0}`). Hoặc đơn giản: bỏ opacity:0 mặc định, chỉ animate khi có class.

### 🟠 BUG B — Hero overlay chữ trắng trên ảnh sáng (contrast)
- `.hero-visual::after` gradient chỉ tối đáy (0.05→0.55). Ảnh factory sáng → chữ "Xưởng May..." khó đọc.
- **Fix:** tăng gradient (0.25→0.75) hoặc thêm text-shadow vàng/trắng.

### 🟠 BUG C — Factory grid 4 ảnh lệch hàng trên tablet
- `minmax(240px,1fr)` → 4 cột hẹp trên màn ~800px dễ vỡ. **Fix:** `repeat(auto-fit,minmax(260px,1fr))` hoặc media query 2 cột.

### 🟡 BUG D — Hero visual `min-height:420px` lệch với text bên trái trên desktop
- Grid `1.1fr/0.9fr`, ảnh cao cố định 420px trong khi text có thể cao/thấp hơn → không cân. **Fix:** align-items stretch hoặc đặt min-height linh hoạt.

### 🟡 BUG E — Nav mobile: lang-toggle + CTA đè lên hamburger
- `.nav-links` mobile hiện thành column nhưng lang-toggle/cta chưa style riêng → lộn xộn. **Fix:** wrap nav-actions, style mobile rõ ràng.

## 4. STOCK IMAGES (đã verify 200, Unsplash CDN)
- Hero: `photo-1581091226825-a6a2a5aee158` (factory worker)
- Factory grid: `1581092160562`, `1605908502724`, `1531973576160`, `1518770660439`
- Products/QC: `1553062407`, `1590874103328`, `1548036328`, `1600857062241`
→ Khi có ảnh xưởng MTS thật, thay `src` các chỗ này.

## 5. LANGUAGE TOGGLE
- Robust: `DOMContentLoaded` + `addEventListener`, localStorage persist. CSS:
  `body:not(.show-en) [lang="en"]{display:none}` / `body.show-en [lang="vi"]{display:none}`.
- KHÔNG dùng inline onclick. KHÔNG xoá class `show-en` logic.

## 6. TEST SAU KHI FIX
- Mở `index.html` trực tiếp (file://) → phải thấy TOÀN BỘ nội dung (không trắng).
- Bấm EN/VI → chỉ 1 ngôn ngữ hiện, không lẫn.
- Resize 375 / 768 / 1200px → không vỡ.
- Reduced-motion: animation tắt, nội dung vẫn hiện.

## 7. PUSH
```
git add index.html
git commit -m "ui: fix reveal/hero/factory per OpenDesign review"
git push origin master
```
Vercel auto-deploy. Không cần token (anh đã link repo).
