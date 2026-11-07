# SwarmOps — 58 AI Agents soạn thư mời trong 10 giây

## Khởi động

Mở file index.html trong Chrome/Edge/Firefox, hoặc truy cập https://xulytiengviet.github.io/swarm-AI/ sau khi GitHub Pages đã bật.

- Chạy lại: dựng lại từ trang giấy trắng.
- Tạm dừng / Tiếp tục: dừng hoặc chạy tiếp đồng hồ.
- Thanh tiến trình: tua đến thời điểm bất kỳ.
- Tốc độ: 0.5×, 1×, 2×. Ở 1×, tổng thời gian 10 giây.
- Khi kết thúc: Sao chép nội dung, hoặc Xuất PDF qua hộp thoại in trình duyệt.

## Cấu trúc

- 58 con trỏ trên trình duyệt: đại diện trực quan cho các tác tử.
- 8 nhóm: Điều phối (6), Bố cục (8), Nội dung (8), Ngôn ngữ (8), Thời gian và sự kiện (7), Thiết kế (7), Kiểm định (7), Xuất bản (7).
- 16 đầu việc soạn thảo văn bản; timeline 0–10 giây; nhật ký sự kiện; 4 kiểm định giả lập.
- Thư mời khổ A4 bằng tiếng Việt, có thể lưu PDF từ trình duyệt.

## Bật GitHub Pages

1. Mở https://github.com/xulytiengviet/swarm-AI/settings/pages
2. Ở Build and deployment chọn Source = GitHub Actions.
3. Mở tab Actions → Deploy SwarmOps demo, nhấn Run workflow nếu cần.
4. Khi workflow thành công, mở https://xulytiengviet.github.io/swarm-AI/

Workflow chỉ đưa file index.html vào trang công khai, không đăng tải mã extension.

## Giới hạn quan trọng

Đây là mô phỏng frontend, không có 58 LLM thực sự suy luận. Các đầu việc và cổng kiểm tra được điều khiển theo kịch bản để minh họa phương pháp phối hợp, không phải kết quả xác thực thực nghiệm. Mẫu thư có ngày, giờ, địa điểm và người đại diện dạng placeholder phải sửa trước khi gửi thật.

Mã HTML demo được viết độc lập, không sao chép động cơ hoạt họa từ tiện ích Chrome gốc. Phần fork từ DhvanilPatel/swarm-cursors được giữ nguyên và có lưu ý về tình trạng giấy phép trong README.

## Lộ trình vận hành AI thật

Tạo orchestrator; định nghĩa API nhiệm vụ cho từng nhóm; kết nối LLM và công cụ; phát sự kiện theo WebSocket/SSE vào dashboard; thực hiện kiểm chứng nội dung trước khi xuất bản. Khi chạy thật, không cam kết hoàn thành đúng 10 giây.
