# 🎮 Game Portal

Cổng game HTML5 tĩnh, xây bằng **Jekyll** — build và host miễn phí trên **GitHub Pages**.

## 🚀 Chạy ở local

Yêu cầu cài [Ruby](https://www.ruby-lang.org/vi/documentation/installation/) (kèm Bundler):

```bash
bundle install        # lần đầu
bundle exec jekyll serve
```

Mở trình duyệt tại **http://127.0.0.1:4000**.

> Nếu repo nằm ở `https://github.com/<user>/<user>.github.io` thì để nguyên `baseurl` rỗng trong `_config.yml`.
> Nếu repo tên khác (ví dụ `game-portal`), bỏ comment dòng `baseurl: "/game-portal"`.

## 📦 Deploy lên GitHub Pages

1. Push code lên branch `main` của repo GitHub.
2. Vào **Settings → Pages**, chọn:
   - Source: **Deploy from a branch**
   - Branch: `main` — thư mục `/ (root)`
3. Chờ ~1–2 phút, trang sẽ chạy tại `https://<username>.github.io/<repo>/`.

GitHub Pages tự nhận diện Jekyll và build — **không cần cấu hình gì thêm**.

## ➕ Thêm game mới

**Cách 1 — Game tự host (khuyên dùng):**
1. Tạo thư mục `assets/games/<ten-game>/` và bỏ file `index.html` của game vào.
2. Tạo file `_games/<ten-game>.md`:

```yaml
---
title: Tên Game
description: Mô tả ngắn hiện trên thẻ game.
gradient: linear-gradient(135deg, #7c5cff, #22d3ee)   # màu nền thẻ game
embed_url: /assets/games/<ten-game>/index.html        # link nhúng iframe
tags: [Arcade, Hành động]
plays: 1.2k
mobile: true
---

Nội dung hướng dẫn chơi (Hỗ trợ Markdown)...
```

**Cách 2 — Game host ngoài:** điền `embed_url` là URL đầy đủ (site đích phải cho phép nhúng iframe).

Trang game tự sinh tại `/games/<ten-game>/`.

## 📁 Cấu trúc thư mục

```
├── _config.yml          # Cấu hình Jekyll
├── _layouts/            # Khung trang: default, game
├── _includes/           # header, footer
├── _games/              # Danh mục game (mỗi file .md = 1 game)
├── assets/
│   ├── css/style.css    # Giao diện toàn site
│   └── games/           # File game HTML5 tự host
├── index.html           # Trang chủ (lưới game + tìm kiếm)
└── Gemfile
```
