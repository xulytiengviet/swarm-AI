# SwarmOps — Thiệp mời K28 / 33 Agents / 33 giây

Xem trang: https://xulytiengviet.github.io/swarm-AI/

## Giao diện
- Một thiệp K28 lớn ở giữa, nền đỏ bordo.
- Chỉ hai nhãn “33 Agents” và “33s” cùng thanh tiến trình mỏng.
- 33 con trỏ mô phỏng chia 33 ô, lần lượt tái dựng ảnh suốt 33 giây.
- Chạm thanh tiến trình hoặc thiệp sau khi hoàn tất để chạy lại.
- Dòng mời mới: “cùng các bạn chuyên ngành Kinh tế, Khóa 28”.

## Ảnh và trạng thái
- Ảnh nền gốc: `assets/k28-invitation.webp`.
- Văn bản được thay ngay trên bản dựng trong Canvas ở `index.html`; **WebP nguồn trong repository chưa bị thay thế**. Khi cần lưu mới ảnh tĩnh đúng văn bản, hãy xuất bản kết quả Canvas ra một tài nguyên riêng.
- Các hoạt động 33 Agents và tốc độ là mô phỏng frontend, không phải tác vụ AI thật.

## GitHub Pages
- Nhánh `gh-pages` giữ bản web độc lập có thể xuất bản từ **Settings → Pages → Deploy from a branch → gh-pages /(root)**, không phụ thuộc Actions runner.
- Sau khi GitHub xuất bản, dùng Ctrl+F5 nếu trình duyệt vẫn lưu bản cũ.

## Giấy phép mã gốc
Repo kế thừa Swarm Rebuild từ DhvanilPatel/swarm-cursors. Mã trang SwarmOps mới được viết độc lập và không trích lại engine hoạt họa vốn chưa có giấy phép rõ ràng.
