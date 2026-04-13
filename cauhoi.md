1. Tại sao phải dùng Nginx làm Reverse Proxy mà không trỏ thẳng Tunnel vào Node-RED?
   Không nên trỏ thẳng vì:

Node-RED không tối ưu bảo mật khi exposed trực tiếp
Khó quản lý nhiều service

Dùng Nginx vì:

Làm cổng trung gian (Reverse Proxy)
Hỗ trợ:
SSL/HTTPS
Auth (xác thực)
Routing nhiều service (/app1, /app2)
Ẩn backend (Node-RED không lộ trực tiếp)
Kết luận: Nginx giúp tăng bảo mật và quản lý hệ thống tốt hơn
2. Sự khác biệt giữa việc Mount file và Mount thư mục trong Docker là gì?
Mount file:
Ánh xạ một file cụ thể
Ví dụ: nginx.conf
Dùng cho cấu hình
Mount thư mục:
Ánh xạ cả thư mục
Ví dụ: thư mục chứa HTML, CSS, JS
Dùng cho dữ liệu/web
Kết luận:

File → cấu hình
Thư mục → dữ liệu
3. Nếu thay đổi file index.html ở máy Ubuntu, nội dung trên web có thay đổi ngay không? Tại sao?
Có (thường là ngay lập tức)

Vì:

Docker dùng bind mount
Container đọc trực tiếp file từ máy host

📌 Lưu ý:

Nếu chưa thấy thay đổi → nhấn Ctrl + F5 để reload

4. docker-compose.yml khai báo các services có phần restart: always hoặc restart: unless-stopped : chúng để làm gì?
restart: always
Container luôn tự khởi động lại
Kể cả khi reboot máy
restart: unless-stopped
Tự khởi động lại
Trừ khi bạn đã dừng thủ công

Mục đích:

Giữ service luôn chạy
Tăng độ ổn định hệ thống

5. Cách khai báo để tất cả các services đều dùng chung 1 network? lợi ích của việc khai báo này là gì? Sửa đổi file docker-compose để tất cả các service đều dùng chung 1 network.
Cách khai báo:
networks:
  mynetwork:

services:
  nginx:
    networks:
      - mynetwork

  nodered:
    networks:
      - mynetwork
Lợi ích:
Container giao tiếp bằng tên service
Ví dụ: http://nodered:1880
Không cần mở nhiều port ra ngoài
Tăng bảo mật (mạng nội bộ)

6. Tìm cách đưa Cloudflare Token vào trong file .env rồi sau đó thêm .env vào file .gitignore trước khi push code lên github. Tại sao nói đây là điều quan trọng về bảo mật mã nguồn?
File .env
CLOUDFLARE_TOKEN=abc123xyz
File .gitignore
.env
Ý nghĩa bảo mật:
Token là thông tin nhạy cảm
Nếu bị lộ:
Có thể bị chiếm quyền hệ thống
Bị tấn công

👉 Kết luận: Không bao giờ push token lên GitHub

7. Tại sao chúng ta nên thêm hậu tố :ro khi mount file cấu hình Nginx?
Ví dụ:

./nginx.conf:/etc/nginx/nginx.conf:ro
:ro = read-only (chỉ đọc)

👉 Lợi ích:

Container không thể sửa file
Tránh lỗi cấu hình
Tăng bảo mật

8. Khi dùng Cloudflare Tunnel: có cần thiết phải mở cổng cho các service nữa không?
👉 Không cần

Vì:

Tunnel tạo kết nối từ trong ra ngoài (outbound)
Không cần mở port inbound
So sánh:
NAT port → cần mở port
Cloudflare Tunnel → không cần

👉 Kết luận:

An toàn hơn
Dễ triển khai hơn
