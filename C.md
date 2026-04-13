C. Cấu hình docker compose:
Tạo thư mục: ~/myapp
Chuyển vào trong thư mục ~/myapp
Tạo thư mục: ./myweb
Tạo file ./myweb/index.html (với nội dung là thông tin cá nhân của em)
Tạo file docker-compose.yml để nó sẽ có các dịch vụ sau:
Khai báo sử dụng nodered/node-red, cổng 1880, dữ liệu nằm tại thư mục ./nodered
Khai báo sử dụng nginx, cổng 80, cấu hình trong file ./nginx/nginx.conf
Mount thư mục ./myweb thành thư mục /myweb trong nginx
Mount file ./nginx/nginx.conf vào file /etc/nginx/nginx.conf trong nginx
Edit file ./nginx/nginx.conf để:
Cấu hình web server cổng 80
server_name là sub-domain (sub-domain tuỳ ý của em)
location / trỏ tới root là thư mục /myweb
location /api dùng proxy_pass trỏ tới 1 (hoặc nhiều) node http_in của nodered
Edit file ./nodered/settings.js để nodered bắt buộc đăng nhập
Chạy docker-compose lần đầu để Node-RED tự sinh file cấu hình trong thư mục ./nodered, sau đó mới tiến hành sửa settings.js và restart lại container

BÀI LÀM
1. Tạo thư mục: ~/test$
mkdir ~/myapp
2. Chuyển vào trong thư mục ~/myapp
cd ~/test
3. Tạo thư mục: ./test
<img width="829" height="170" alt="Ảnh chụp màn hình 2026-04-13 105601" src="https://github.com/user-attachments/assets/c148ee2a-1d11-4418-a389-f55f762ed176" />
4. Tạo file ./myweb/index.html (với nội dung là thông tin cá nhân của em)
nano myweb/index.html

<img width="1066" height="817" alt="Ảnh chụp màn hình 2026-04-13 213820" src="https://github.com/user-attachments/assets/7433498a-1b1d-4b7f-be43-04c05c560439" />
5. Tạo file docker-compose.yml để nó sẽ có các dịch vụ sau:
tạo file docker-compose.yml
gõ: nano docker-compose.yml để tạo file

<img width="960" height="809" alt="Ảnh chụp màn hình 2026-04-13 213954" src="https://github.com/user-attachments/assets/67507bbc-4546-4277-8a6b-55b3269f3c22" />

tạo thư mục Nginx và nodered ( vì máy chưa có)
mkdir nginx
mkdir nodered
