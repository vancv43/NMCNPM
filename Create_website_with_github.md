Tạo trang web với Github Pages
GitHub Pages là một dịch vụ tuyệt vời từ GitHub, cho phép bạn triển khai các website tĩnh (HTML, CSS, JavaScript) một cách nhanh chóng và hoàn toàn miễn phí. Dưới đây là các bước thực hiện:

1.Tạo Repository Trên GitHub
Đăng nhập vào tài khoản GitHub.
Nhấp vào New Repository để tạo một repository mới. image.png
Đặt tên repository là username.github.io (thay username bằng tên tài khoản của bạn). image.png
Chọn Public và nhấn Create Repository.
2.Chuẩn bị nội dung cho website ở máy cá nhân
Để đơn giản, mình có 1 file index.html với nội dung là "Hello World" và một file README.md image.png
Sau đó bạn cần đẩy chúng lên repo bạn vừa tạo bằng các câu lệnh:
Mở terminal (hoặc Command Prompt) và điều hướng đến thư mục chứa source chuẩn bị của bạn:
Tạo kho git cục bộ: bash git init
Bạn có thể chỉ định việc thêm file hoặc thư mục để đẩy lên. Ở đây cho dễ dàng, mình sử dụng luôn bash git add .
Thực hiện commit: ```` bash git commit -m "noi dung"
Đổi tên nhánh hiện tại thành main: bash git branch -M main (Do tiêu chuẩn hiện tại, Git khuyến nghị sử dụng main thay vì master làm tên mặc định cho nhánh chính)
Liên kết kho Git cục bộ của bạn với kho lưu trữ trên GitHub: bash git remote add origin https://github.com/username/username.github.io.git ((thay username bằng tên tài khoản của bạn)
Đẩy (push) các thay đổi cục bộ từ nhánh main lên kho lưu trữ từ xa (origin): bash git push -u origin main
3.Cấu đặt GitHub Pages
Truy cập vào kho lưu trữ GitHub vừa tạo của bạn
Đi đến phần cài đặt (Settings) > Chọn mục Pages
Cấu hình nguồn xuất bản (Source):
Trong mục Build and Deployment, bạn sẽ thấy Source.
Chọn Deploy from a branch nếu muốn sử dụng nhánh main.
Xác định nhánh xuất bản: chọn Branch: main và Folder: /(root).
Nhấn Save để lưu cài đặt và chờ đợi. image.png
Bạn có thể vào mục Actions để kiểm tra đã build thành công chưa image.png
Đây là kết quả image.png
Tài Liệu Tham Khảo
https://docs.github.com/fr/pages/getting-started-with-github-pages/creating-a-github-pages-site

