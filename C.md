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

Chạy docker-compose lần đầu để Node-RED tự sinh file cấu hình trong thư mục ./nodered, sau đó mới tiến hành sửa settings.js và restart lại 
container

BÀI LÀM

1. Tạo thư mục: ~/test$

mkdir ~/myapp

2. Chuyển vào trong thư mục ~/myapp


cd ~/test


3. Tạo thư mục: ./test

<img width="1078" height="193" alt="Ảnh chụp màn hình 2026-04-13 213756" src="https://github.com/user-attachments/assets/43e7b403-fe60-401f-8e16-9737c71c4ba0" />

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

<img width="1078" height="193" alt="Ảnh chụp màn hình 2026-04-13 213756" src="https://github.com/user-attachments/assets/9ad15504-5a57-49a7-9563-ae77b8848596" />

Khai báo sử dụng nodered/node-red, cổng 1880, dữ liệu nằm tại thư mục ./nodered

Khai báo sử dụng nginx, cổng 80, cấu hình trong file ./nginx/nginx.conf

nano nginx/nginx.conf

<img width="968" height="995" alt="Ảnh chụp màn hình 2026-04-13 213917" src="https://github.com/user-attachments/assets/05a488a3-b9f6-4923-b4ad-276088e9aa02" />
<img width="951" height="883" alt="Ảnh chụp màn hình 2026-04-13 215141" src="https://github.com/user-attachments/assets/c51d74dc-a9a9-41cb-86db-bad502da1d09" />

Mount thư mục ./myweb thành thư mục /myweb trong nginx
<img width="1916" height="1031" alt="Ảnh chụp màn hình 2026-04-13 214459" src="https://github.com/user-attachments/assets/b2888532-f4fd-47b0-b8f9-f351b91333c6" />
Mount file ./nginx/nginx.conf vào file /etc/nginx/nginx.conf trong nginx
<img width="960" height="809" alt="Ảnh chụp màn hình 2026-04-13 213954" src="https://github.com/user-attachments/assets/867b8cac-50ca-4f92-8d7f-f3bc22055191" />
6. Edit file ./nginx/nginx.conf để:
- Cấu hình web server cổng 80
  + Mở file cấu hình nano nginx/nginx.conf
<img width="968" height="995" alt="Ảnh chụp màn hình 2026-04-13 213917" src="https://github.com/user-attachments/assets/855f0ea3-9cef-4b31-b4c9-1ce35479b358" />
- location / trỏ tới root là thư mục /myweb
  + Mở file cấu hình nano nginx/nginx.conf
<img width="968" height="995" alt="Ảnh chụp màn hình 2026-04-13 213917" src="https://github.com/user-attachments/assets/b1b26487-e96e-4a96-bf9e-bada14f1e22f" />
<img width="1916" height="1031" alt="Ảnh chụp màn hình 2026-04-13 214459" src="https://github.com/user-attachments/assets/fcc2bb07-536d-489a-b23d-1ebaf5428d88" />
- location /api dùng proxy_pass trỏ tới 1 (hoặc nhiều) node http_in của nodered
  + Tạo api trong node-Red
    <img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-13 221233" src="https://github.com/user-attachments/assets/e9a53e24-90b4-4a5f-8469-6deae9a033c4" />
<img width="1911" height="1035" alt="Ảnh chụp màn hình 2026-04-13 215302" src="https://github.com/user-attachments/assets/bd64d635-989d-4389-b671-044349ccd158" />
7. Edit file ./nodered/settings.js để nodered bắt buộc đăng nhập
  - Chạy docker-compose lần đầu để Node-RED tự sinh file cấu hình trong thư mục ./nodered, sau đó mới tiến hành sửa settings.js và restart lại container
    <img width="951" height="340" alt="Ảnh chụp màn hình 2026-04-13 221008" src="https://github.com/user-attachments/assets/34850f8e-d1c7-47cb-9d0f-9cb21048e8cf" />
    <img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-13 221211" src="https://github.com/user-attachments/assets/69de41e5-6f63-4e68-a42d-dbf4a809b2fe" />
