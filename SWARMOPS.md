## Khắc phục Actions không được cấp runner (07/11/2026)

GitHub Actions run [42328432387](https://github.com/xulytiengviet/swarm-AI/actions/runs/42328432387) thất bại nhiều lần **trước khi chạy bất kỳ bước nào**: runner_id=0, steps=[], thời lượng sử dụng runner 0ms. Đây là dấu hiệu lỗi cấp phát/khởi tạo runner, **không có bằng chứng file ảnh hay cú pháp HTML gây lỗi**. Không thể kết luận nguyên nhân hạ tầng chính xác vì GitHub không trả log chi tiết/annotations qua kết nối hiện tại.

### Giải pháp không cần runner — dùng nhánh gh-pages

Nhánh [gh-pages](https://github.com/xulytiengviet/swarm-AI/tree/gh-pages) đã được tạo độc lập và chứa đủ:

- `index.html` — giao diện mô phỏng 58 con trỏ/16 vùng/10 giây.
- `assets/k28-invitation.webp` — ảnh thư mời USSH Địa lý K28.
- `.nojekyll` — xuất bản file tĩnh trực tiếp.

**Cần thao tác một lần trên giao diện GitHub:**
1. Mở [Settings → Pages](https://github.com/xulytiengviet/swarm-AI/settings/pages).
2. Mục **Build and deployment**, đổi **Source** từ **GitHub Actions** sang **Deploy from a branch**.
3. Chọn **Branch: gh-pages**, thư mục **/(root)** và nhấn **Save**.
4. Khi GitHub thông báo đã xuất bản, truy cập https://xulytiengviet.github.io/swarm-AI/ và dùng Ctrl+F5 để bỏ cache cũ.

Từ nay workflow Actions trên `main` chỉ chạy khi bấm **Run workflow**; nó không tự chạy theo push, tránh lặp lại lỗi cấp runner. **Không cần chạy lại job 42328432387** để sử dụng chế độ Pages từ nhánh. Trường hợp GitHub báo lỗi ngay cả khi dùng branch, cần kiểm tra mục thông báo tài khoản, Pages settings và khả năng sử dụng GitHub Actions của chủ repository.


---

# SWARMOPS – 58 AI Agents tái dựng thư mời K28 trong 10 giây

**Xem trực tuyến:** https://xulytiengviet.github.io/swarm-AI/

## Nguồn ảnh

- `assets/k28-invitation.webp`: ảnh thư mời gốc “Tọa Độ Thanh Xuân”, USSH – Địa lý K28, do người dùng cung cấp; chuyển từ PNG 1024 × 1536 sang WebP 900 × 1350 để hiển thị nhanh hơn. Không thay nội dung, bố cục hoặc tạo lại thư bằng AI.
- `index.html`: dashboard trực quan tái dựng từng vùng từ ảnh. Khi hoàn thành, hình hiển thị trùng với tài nguyên WebP đã lưu.
- Ngày họp mặt ghi trong ảnh: **14/11/2026**, 12:00 tại cơ sở Linh Xuân; 17:00 tại Harmony Saigon Hotel & Spa.

## Cách sử dụng

1. Mở dashboard. Nếu muốn bắt đầu từ giấy trắng, nhấn **Chạy lại**.
2. Quan sát 58 con trỏ thuộc 8 đội phân vai, hoạt động trên **16 vùng** của thư mời.
3. Dừng/chạy tiếp, tua thanh tiến trình 0–10 giây hoặc đổi tốc độ 0.5×/1×/2×.
4. Khi hoàn thành, **Xem ảnh gốc**, **Sao chép** nội dung hoặc **Xuất PDF** bằng hộp thoại in của trình duyệt.

## Các nhóm mô phỏng

Điều phối (6), Bố cục (8), Nội dung (8), Ngôn ngữ (8), Thời gian & sự kiện (7), Thiết kế (7), Kiểm định (7), Xuất bản (7). Tổng cộng **58 con trỏ**. Các nhóm là vai diễn trực quan trong trình duyệt, không phải các tiến trình LLM độc lập.

## Quy trình 10 giây

- 0–2s: tập hợp bầy đàn, bắt đầu dựng logo 15 năm và cảnh quan.
- 2–4s: hiện chữ “Tọa Độ Thanh Xuân”, “Thư Mời”, tên người nhận.
- 4–6s: dựng văn bản họp mặt và lời tri ân.
- 6–8s: ghép hai khung lịch và địa điểm.
- 8–10s: ghép chi tiết cuối, kiểm tra mô phỏng, hoàn thành.

Mô phỏng sử dụng Canvas API vẽ lại từng vùng bằng `drawImage` trên **cùng một ảnh nguyên bản**, không phải mô hình text-to-image. Mỗi Agent là một con trỏ DOM/SVG tương tác với vùng nhiệm vụ. 4 cổng QA chỉ có vai trò minh họa.

## GitHub Pages

Workflow `.github/workflows/pages.yml` sao chép `index.html` và `assets/` vào artifact GitHub Pages. Trong **Settings → Pages**, chọn Source = **GitHub Actions**. Chạy workflow **Deploy SwarmOps demo** khi cần.

## Lưu ý kỹ thuật

- 10 giây được tính ở tốc độ 1× trong lúc tab đang hoạt động; trình duyệt có thể giảm tốc hoạt họa ở tab nền.
- Có chế độ giảm chuyển động theo cài đặt hệ điều hành; sử dụng phím Space để phát/dừng khi không đặt con trỏ trong ô nhập liệu.
- Mã dashboard viết độc lập, giữ nguyên thư mục extension fork `swarm-rebuild/`. README gốc nêu các hạn chế giấy phép của mã Swarm Rebuild.
- Không có backend; nếu cần AI thật, bổ sung orchestrator, LLM, phân nhiệm vụ thực, nhật ký SSE/WebSocket và bộ đánh giá chất lượng.
