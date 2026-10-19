# Nhắc Tốc Độ — dữ liệu và trang web

Repo công khai này chỉ chứa hai thứ:

- **Trang web** (GitHub Pages, thư mục `docs/`): trang giới thiệu và
  [chính sách quyền riêng tư](https://kenhtaymay.github.io/nhac-toc-do/privacy/).
- **Dữ liệu bản đồ** cho ứng dụng, đăng ở [Releases](https://github.com/kenhtaymay/nhac-toc-do/releases):
  mỗi bản là một tag `ktm-<data_version>` gồm `ktm.d2t` (đã mã hoá, có chữ ký) và `manifest.json` (có chữ ký).

Ứng dụng luôn đọc bản mới nhất qua link cố định:

```
https://github.com/kenhtaymay/nhac-toc-do/releases/latest/download/manifest.json
```

Mã nguồn ứng dụng không nằm ở đây.

## Đăng bản dữ liệu mới

Chạy từ repo mã nguồn của ứng dụng, với khoá thật nằm ngoài mọi repo:

```
python -I tools/ktm/release.py <ktm_all.db> --keys D:/Keys/nhac-toc-do --github kenhtaymay/nhac-toc-do --publish
```

Công cụ sẽ đóng gói, tự kiểm lại file, ký manifest và tạo release mới. `data_version` của bản mới phải lớn hơn bản
đang có, nên không thể vô tình đăng lùi.
