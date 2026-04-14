# F. Gỡ lỗi
1 nếu có lỗi xẩy ra trong quá trình triển khai docker compose up -d
- Kiểm tra nhanh: docker compose ps giúp biết container nào đang chạy xem log, ví dụ: docker logs mynginx docker logs myapi
  <img width="1876" height="173" alt="Ảnh chụp màn hình 2026-04-13 222708" src="https://github.com/user-attachments/assets/896d71a5-51a6-4569-b566-58f0952a451a" />
<img width="960" height="143" alt="Ảnh chụp màn hình 2026-04-13 222736" src="https://github.com/user-attachments/assets/361ec704-0135-4f6f-b1e7-a9c1b06d6678" />
2. Thêm healthcheck cho myapi trong file docker-compose.yml
  <img width="964" height="1079" alt="Ảnh chụp màn hình 2026-04-13 223222" src="https://github.com/user-attachments/assets/53002202-cbcc-4990-ace1-a59f4412c75d" />
3. giới hạn resource cho một service: (tránh việc 1 service chiếm quá nhiều ram)
  <img width="964" height="1079" alt="Ảnh chụp màn hình 2026-04-13 223222" src="https://github.com/user-attachments/assets/f02e33c9-20d7-4d50-9202-ec6b1c8da0c2" />
  <img width="955" height="354" alt="Ảnh chụp màn hình 2026-04-13 223442" src="https://github.com/user-attachments/assets/30c17963-e896-4217-b8bb-bf556073dd03" />
  <img width="1905" height="187" alt="Ảnh chụp màn hình 2026-04-13 223912" src="https://github.com/user-attachments/assets/c450aa59-198f-45e6-be73-79e29592b76a" />

- sử dụng lệnh: docker compose stats để quan sát lượng ram sử dụng bởi mỗi service
  <img width="1322" height="145" alt="Ảnh chụp màn hình 2026-04-13 223942" src="https://github.com/user-attachments/assets/da2ed69c-ca4c-4ba2-8751-a15a57735154" />
