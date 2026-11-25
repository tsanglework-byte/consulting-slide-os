# Consulting Slide OS
Bộ quy trình tạo đúng một slide Business Case theo **Universal Consulting Slide Prompt v2 (visual-first)** do người dùng cung cấp ngày 25/11/2026. Không liên kết hay đại diện cho McKinsey, BCG, Bain hoặc think-cell.
## Bắt đầu
- `skills/consulting-slide-design/` là skill chính độc lập, dùng được cho IMAGE, BLUEPRINT, PPTX tuỳ công cụ. Cài skill này trước.
- Ba skill phụ `consulting-storytelling`, `consulting-chart-design`, `consulting-slide-review` chỉ dùng khi muốn xử lý riêng một bước.
- Xem [docs/setup.md](docs/setup.md) để cài đặt; [docs/ppt-master.md](docs/ppt-master.md) cho công cụ sản xuất tùy chọn; [tests/evaluation-cases.md](tests/evaluation-cases.md) để kiểm thử.
## Nguồn chuẩn duy nhất
`skills/consulting-slide-design/references/universal-slide-prompt-v2.md` là bản sao byte-for-byte của file Markdown người dùng cung cấp, gồm cả hướng dẫn tiếng Việt và SLIDE BRIEF. V5.0 đã bị loại khỏi bản hoạt động, không trộn hai bộ quy tắc. Bản hỗ trợ chỉ hướng dẫn xử lý thiếu dữ liệu, xác minh tên Library và giới hạn công cụ; không chỉnh sửa prompt gốc.
## Quy tắc triển khai
Không bịa số liệu để đạt mật độ visual, không giả lập tên Library đã xác minh, không tuyên bố kiểm tra chưa chạy. Build Sheet, Appendix Note và Quality Check là tài liệu ngoài slide. Private repo được khuyến nghị. Không chứa dữ liệu nội bộ, mã nguồn ppt-master, license think-cell hoặc engine tạo slide độc lập.
## Version 0.2.0
Kiểm tra cấu trúc, đóng gói, cài bản sao local và hash prompt; chưa kiểm thử việc sinh slide thực tế trên các nền tảng.
