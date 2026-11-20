# Phần mềm Quản lý dữ liệu dân cư (GitHub Pages)

## Triển khai
1. Tạo repository GitHub mới. Khuyến nghị repository **Private** trong quá trình rà soát; GitHub Pages có thể yêu cầu gói/quyền phù hợp nếu repo private.
2. Tải lên `index.html`, `.gitignore` và `README.md`. Không tải lên bất kỳ tệp Excel chứa dữ liệu dân cư thật.
3. Vào **Settings → Pages**. Ở **Build and deployment**, chọn **Deploy from a branch**.
4. Chọn nhánh `main`, thư mục `/(root)`, nhấn **Save**.
5. Chờ GitHub hoàn tất triển khai, mở URL Pages được cung cấp và thử bằng một tệp Excel giả lập đã ẩn danh.
6. Kiểm tra nhập tệp, các tab, lọc, thống kê, xuất từng danh sách, xuất công dân đủ 18 tuổi và xuất tổng hợp trước khi dùng chính thức.

## Lưu ý thư viện
Trang hiện dùng các thư viện trình duyệt qua CDN với phiên bản cố định: SheetJS 0.18.5, ExcelJS 4.3.0, FileSaver.js 2.0.5 và Chart.js 4.4.8. Do môi trường xử lý hiện tại không truy cập được CDN để tải các tệp thư viện, bản này **chưa đóng gói thư viện nội bộ**; khi mở ứng dụng cần có Internet để tải các thư viện. Đây là phần còn lại cần xử lý nếu yêu cầu triển khai hoàn toàn độc lập/offline.

## An toàn dữ liệu
- Chỉ xử lý tệp dân cư trên máy tính được kiểm soát; không dùng máy công cộng.
- Dữ liệu không được gửi tới backend của ứng dụng, nhưng trình duyệt vẫn tải mã thư viện từ các CDN bên ngoài.
- Không commit/push tệp Excel thật; `.gitignore` chỉ là lớp hỗ trợ, không thay thế kiểm tra trước khi commit.
- Trước khi public repository, rà soát toàn bộ lịch sử Git để bảo đảm không có dữ liệu thật từng được commit.
- GitHub Pages là website công khai theo URL; không coi đường dẫn Pages là nơi lưu trữ dữ liệu dân cư.
