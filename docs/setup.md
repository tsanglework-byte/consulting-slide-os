# Hướng dẫn thiết lập

## GitHub (Windows, không cần dòng lệnh)
1. Giải nén repository ZIP. Giữ nguyên thư mục `consulting-slide-os`.
2. Mở GitHub Desktop (https://desktop.github.com/) và đăng nhập.
3. File > Add local repository, chọn thư mục trên. Nếu GitHub Desktop báo chưa phải Git repository, chọn tạo repository tại thư mục hiện có (kiểm tra không tạo thư mục lồng tên giống nhau).
4. Kiểm tra danh sách file, commit nếu cần, chọn Publish repository, giữ `Keep this code private`. Chưa có repository trực tuyến thì không cần tạo thêm một repo trùng tên trên website. Nếu đã tạo repo rỗng online, dùng Clone rồi chép các file bên trong vào thư mục clone, commit và push.

## Claude web/desktop
- Giải nén repository, hoặc tải file ZIP riêng của skill chính được cung cấp. Có thể tạo ZIP skill bằng `python scripts/manage_skills.py package` (Windows có thể dùng `py`).
- Trong Claude, bật khả năng code execution/file creation nếu cần và được phép; Customize > Skills > Create skill > Upload a skill. Chọn `consulting-slide-design.zip` (không chọn ZIP toàn bộ repository). Bật skill. Chỉ upload skill phụ nếu có nhu cầu riêng.
- Project Knowledge có thể thêm master prompt và các reference cần thiết nếu không có chức năng Skills. Đọc tài liệu không đồng nghĩa skill đã được cài. Không đồng bộ tự động ZIP khi thay đổi GitHub; cập nhật và cài lại theo giao diện.
- Nguồn: https://support.claude.com/en/articles/12512180-use-skills-in-claude ; https://support.claude.com/en/articles/12512198-how-to-create-custom-skills

## Claude Code và Codex
- Mở terminal tại thư mục repo, dùng Python 3.10+ đã cài. Chạy `python scripts/manage_skills.py install --agent claude` hoặc `python scripts/manage_skills.py install --agent codex`. Lệnh chỉ sao chép skill chính vào `.claude/skills/` hoặc `.agents/skills/` của repo, không tải mạng và không ghi đè.
- Để dùng cả skill phụ, thêm `--all`. Để cập nhật các bản sao đã cài sau khi xem diff, dùng `--replace`. Không dùng --replace nếu có chỉnh sửa cục bộ cần giữ.
- Khởi động agent trong thư mục repo và kiểm tra skill được nhận diện. Có thể copy thư mục skill vào nơi cài cấp người dùng tương ứng nếu cần dùng cho dự án khác; ưu tiên cấp dự án khi thử nghiệm.
- Nguồn: https://code.claude.com/docs/en/skills ; https://developers.openai.com/codex/skills

## ChatGPT
- Nếu workspace có Skills và cho phép upload: Plugins > Skills > Create > Upload from your computer. Chọn ZIP skill chính; chờ kết quả kiểm tra. Nếu giao diện không hỗ trợ upload, dùng Universal Consulting Slide Prompt v2 và các file reference trong Project hoặc gửi cùng yêu cầu.
- Tài liệu chính thức nêu tính năng Skills dành cho Business, Enterprise, Healthcare và Edu đủ điều kiện; không giả định Plus cá nhân có tính năng này. Codex là môi trường riêng. Kết nối GitHub chỉ cung cấp khả năng tham chiếu theo quyền; không đồng nghĩa cài skill hay có quyền ghi repository.
- Nguồn: https://help.openai.com/en/articles/20001066-skills-in-chatgpt

## Lệnh thử
“Use consulting-slide-design. Create exactly ONE editable consulting-grade slide using the attached data. Apply my Universal Consulting Slide Prompt v2 visual-first standard. All slide text in English. Do not invent evidence. Render and inspect before delivery. Explain the design rationale in Vietnamese.”

Chạy thử bằng dữ liệu giả định trong tests/evaluation-cases.md; không tải dữ liệu nhạy cảm. Đánh giá cùng input trên hai AI. Sau khi sửa skill nguồn, đóng gói lại hoặc cập nhật bản cài. Không có đồng bộ tự động giữa các nền tảng.

## Cập nhật từ 0.1.0
Tắt hoặc thay skill phiên bản cũ trước khi bật phiên bản mới. Với GitHub đã có repo, clone/pull rồi thay các file nguồn theo bản mới (xóa references/master-prompt-v5.md cũ), review diff, commit và push. Chạy install --replace sau khi xem diff nếu đã cài local. Không upload cả ZIP repository vào Claude Skills.
