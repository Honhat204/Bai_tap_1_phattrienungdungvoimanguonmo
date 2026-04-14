# E. Triển khai (level test) ứng dụng
1. Chuyển vào trong thư mục ~/myapp
   <img width="942" height="217" alt="Ảnh chụp màn hình 2026-04-13 221517" src="https://github.com/user-attachments/assets/117c8c2a-2197-4230-be92-60b64f01c485" />
2. Gõ lệnh để docker compose chạy: sẽ run tất cả các service khai báo trong file docker-compose.yml
   <img width="942" height="217" alt="Ảnh chụp màn hình 2026-04-13 221517" src="https://github.com/user-attachments/assets/eca9d296-fb8c-4a97-9ec2-9eab90caed03" />
3. Kiểm tra các container đang chạy trong docker, nếu có cái nào bị restart cần tìm lỗi rồi edit lại docker-compose.yml
- Kiểm tra container có chạy không
  + docker ps
    <img width="1903" height="155" alt="Ảnh chụp màn hình 2026-04-13 221534" src="https://github.com/user-attachments/assets/69a00d46-082b-4179-a72e-cb2d41488b54" />
4. Kiểm tra kiểm thử các service đang chạy độc lập thông qua ip và port của nó: ví dụ mở trình duyệt ip_ubuntu:1880 để check nodered đã chạy chưa
 <img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-13 221233" src="https://github.com/user-attachments/assets/71c9cf22-16b2-41a9-a367-6323e12b69a2" />
<img width="1911" height="1035" alt="Ảnh chụp màn hình 2026-04-13 215302" src="https://github.com/user-attachments/assets/578f3583-f09d-406f-9601-7307dc327e20" />
5. Sử dụng nodered: kéo nodered http_in , http_response, function : để tạo api get đơn giản (dùng cho /api proxy_pass của nginx)
<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-13 221233" src="https://github.com/user-attachments/assets/eb4a204a-f2cc-49f0-8cdb-1d9439b44286" />
<img width="1911" height="1035" alt="Ảnh chụp màn hình 2026-04-13 215302" src="https://github.com/user-attachments/assets/0a341b57-fbe4-44ae-9da6-8be18ba9d42f" />
6. Sửa file ./myweb/index.html : thêm code html+js để sử dụng được api đã khai báo proxy_pass (thực ra là sử dụng nodered http_in hoặc sử dụng service myapi)
<img width="955" height="1072" alt="Ảnh chụp màn hình 2026-04-13 222214" src="https://github.com/user-attachments/assets/32636851-7d9e-4857-bf49-23ccb4a3c59e" />
<img width="1919" height="1074" alt="Ảnh chụp màn hình 2026-04-13 222517" src="https://github.com/user-attachments/assets/9d7895bc-4239-4eba-9720-53578baed90b" />
