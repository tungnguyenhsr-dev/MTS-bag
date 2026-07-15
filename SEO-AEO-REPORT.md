# Báo Cáo SEO/AEO — Minh Tùng Studio (MTS) Website

**Ngày:** 15/07/2026  
**Trang web:** https://mts-bag.vercel.app/  
**Thư mục:** `C:\Users\localadmin\OneDrive\Documents\TOMMY\Efforts\MTS\website\`

---

## Tóm Tắt Công Việc Đã Làm

### 1. Technical SEO — Tệp tin nền tảng

| Việc | Trạng thái |
|------|-----------|
| Tạo `robots.txt` | ✅ Hoàn thành |
| Tạo `sitemap.xml` | ✅ Hoàn thành |
| Tạo `llms.txt` cho AI agents | ✅ Hoàn thành |

- **robots.txt**: Cho phép tất cả AI crawler (GPTBot, ChatGPT-User, PerplexityBot, ClaudeBot, Google-Extended, Bingbot). Có tham chiếu sitemap.
- **sitemap.xml**: Bao gồm index.html và blog.html. Có thể mở rộng sau này.
- **llms.txt**: Tổng quan nhà máy + đường dẫn đến các trang chính + dữ liệu nhà máy cốt lõi.

### 2. Schema Markup (JSON-LD)

| Schema | index.html | blog.html |
|--------|-----------|-----------|
| Organization | ✅ (đã có, giữ nguyên) | — |
| WebSite | ✅ (đã có, giữ nguyên) | — |
| Product (×5) | ✅ (đã có, giữ nguyên) | — |
| FAQPage | ✅ **Mới** (5 câu hỏi) | ✅ **Mới** (3 câu hỏi) |
| BlogPosting (×2) | — | ✅ **Mới** (có dateModified + author) |

### 3. On-Page SEO

| Kiểm tra | index.html | blog.html |
|----------|-----------|-----------|
| Title | ✅ "OEM Bag & Backpack Manufacturer Vietnam \| Minh Tùng Studio" (62 ký tự) | ✅ "Blog — Minh Tùng Studio \| OEM Bag Manufacturer Vietnam" (54 ký tự) |
| Meta description | ✅ 151 ký tự (≤155) | ✅ 132 ký tự (≤155) |
| Canonical URL | ✅ https://mts-bag.vercel.app | ✅ https://mts-bag.vercel.app/blog.html |

### 4. AEO — Content Extractability

| Nội dung | Trạng thái |
|----------|-----------|
| Answer block "OEM là gì?" trong Services | ✅ 40–60 words (EN+VI) |
| Answer block "OEM bag manufacturer là gì?" trên blog Post 1 | ✅ |
| Answer block "Làm sao bắt đầu thương hiệu túi?" trên blog Post 2 | ✅ |
| Bảng so sánh OEM vs ODM | ✅ Trong Services |
| Bảng so sánh chất liệu (Canvas/PU/Nylon/Da) | ✅ Trong Products |

### 5. Freshness Signals

| Tín hiệu | Trạng thái |
|----------|-----------|
| Tác giả (Nguyễn Mạnh Tùng — Founder & Production Director) | ✅ Cả 2 bài blog |
| Ngày cập nhật (Last updated: 2026-07-15) | ✅ Cả 2 bài blog |
| Thời gian đọc (5 min / 6 min) | ✅ Cả 2 bài blog |

### 6. Internal Linking

| Liên kết | Trạng thái |
|----------|-----------|
| blog.html → index.html#services (OEM vs ODM) | ✅ |
| blog.html → index.html#quality (Quality Control) | ✅ |
| blog.html → index.html#products (Material comparison) | ✅ |
| blog.html → index.html#capabilities (Production capabilities) | ✅ |
| blog.html → index.html#contact (Quote request) | ✅ (đã có sẵn) |
| index.html → blog.html (Blog link trong Services) | ✅ |

### 7. Target Query Coverage

| Truy vấn mục tiêu | Matching H2 | Answer block |
|-------------------|-------------|-------------|
| "OEM bag manufacturer Vietnam" | ✅ blog.html #oem-guide | ✅ |
| "bag factory Vietnam" | ✅ Hero section | ✅ |
| "custom backpack OEM" | ✅ Blog + index Products | ✅ |
| "how to start a bag brand" | ✅ blog.html #start-brand | ✅ |
| "find bag manufacturer Vietnam" | ✅ Blog Step 3 | ✅ |
| "gia công túi balo" | ✅ Hero EN+VI | ✅ |
| "xưởng may túi VN" | ✅ index.html #about | ✅ |
| "bag production MOQ" | ✅ Services table + blog | ✅ |

---

## Khuyến Nghị Còn Lại

### ⚠️ Cần làm (ưu tiên cao)

1. **Google Analytics ID**: `G-XXXXXXXXXX` vẫn là placeholder. Cần thay bằng GA4 measurement ID thật.
2. **Domain riêng**: Hiện tại site host trên Vercel (mts-bag.vercel.app). Mua domain riêng (ví dụ: mtsbag.vn, minhtungstudio.com) sẽ tăng độ tin cậy và SEO.
3. **Ảnh sản phẩm thật**: Các ảnh sản phẩm hiện tại là placeholder. Chụp ảnh xưởng thật và sản phẩm thật sẽ cải thiện E-E-A-T đáng kể.

### 💡 Nên làm (ưu tiên trung bình)

4. **Backlinks**: Tạo Wikipedia entry, đăng bài trên LinkedIn/Medium, tham gia diễn đàn (Reddit r/reps, fashion communities) để tăng dẫn chứng từ bên thứ ba — đây là yếu tố AI Overview ưu tiên nhất.
5. **Google Search Console & Bing Webmaster Tools**: Submit sitemap.xml để theo dõi index status.
6. **Google Business Profile**: Nếu có địa chỉ văn phòng/workshop, tạo GB Profile để xuất hiện trong local pack và AI Overviews.
7. **PageSpeed**: Kiểm tra Core Web Vitals sau khi deploy — đặc biệt là LCP (ảnh hero) và CLS.
8. **Portfolio PDF**: File `MTS-Portfolio.pdf` được link trong trang — nên compress và kiểm tra không lỗi.

### 🔮 Dài hạn

9. **Blog posts thành trang riêng**: Tách mỗi blog post thành file HTML riêng (`/blog/oem-bag-manufacturer-vietnam.html`) để có URL độc lập, dễ index hơn.
10. **Pricing page public**: Thêm `/pricing.md` với bảng giá minh bạch — giúp AI agent có thể đọc và so sánh.
11. **Hreflang**: Khi có domain riêng, thêm hreflang cho EN/VI để Google hiểu cấu trúc song ngữ.
12. **Chứng chỉ quốc tế**: Khi đạt BSCI/ISO 9001, cập nhật ngay lên trang và JSON-LD.

---

## Kết Luận

Site đã đạt baseline SEO/AEO cơ bản: robots.txt cho phép AI crawler, sitemap + llms.txt tồn tại, schema JSON-LD hợp lệ (Organization, WebSite, Product, FAQPage, BlogPosting), meta title/description đúng độ dài, answer blocks và comparison tables cho AI extractability, freshness signals có trên blog posts, và internal linking hai chiều giữa index ↔ blog.

Các bước tiếp theo quan trọng nhất: **mua domain riêng**, **GA4 ID thật**, và **xây dựng backlinks từ bên thứ ba**.
