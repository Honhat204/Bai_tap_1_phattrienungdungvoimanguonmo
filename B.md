B. Cài đặt Ubuntu + Docker
Cài đặt hệ điều hành Ubuntu 24.04.4 LTS
Sử dụng một trong các công cụ để giả lập: HyperV (có sẵn của windows), VirutualBox (Miễn phí), VM_Ware (bản quyền)
Download file iso để cài đặt.
Cấu hình mạng trong Ubuntu (và công cụ giả lập) để cho phép truy cập SSH vào Ubuntu từ cmd của windows
Ví dụ:

để ssh tới ubuntu ở ip 192.168.100.123, user là admin thì mở CMD trên windows,
gõ lệnh: ssh admin@192.168.100.123
hệ thống sẽ yêu cầu nhập password (chú ý : password sẽ không hiện ra)
sau khi login thành công sẽ thấy màn hình chào hỏi của ubuntu
Tìm hiểu các lệnh cơ bản của ubuntu
Các lệnh cần tìm hiểu:

Liệt kê các file trong thư mục: ls
Tạo thư mục: mkdir nameFolder
Chuyển thư mục làm việc: cd path
Copy file: cp file_nguồn path/file_đích
Thay đổi quyền thao tác file: sudo chmod xxx filename
Edit file: sudo nano tenfile
CTRL+o : lưu nội dung sau khi edit
CTRL+x : thoát edit file
Xem ip của máy ubuntu: ip -4 addr
Cài đặt docker cho Ubuntu
Kiểm tra phiên bản docker vừa cài đặt, kiểm tra phiên bản của docker compose
Cấu hình để docker chạy mà không cần tiền tố sudo
Tìm hiểu tập lệnh của docker và docker compose
Đảm bảo tường lửa trên Ubuntu đã cho phép các cổng 80, 1880, 9630 (Lệnh: sudo ufw allow ...)
BÀI LÀM
1. Cài đặt hệ điều hành Ubuntu 24.04.4 LTS
Cài đặt hệ điều hành Ubuntu 24.04.4 LTS

Sử dụng một trong các công cụ để giả lập: VM_Ware

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/af84840b-dd90-49e1-9a5a-25c608f49240" />

Cài và bật SSH trong Ubuntu
<img width="901" height="271" alt="Ảnh chụp màn hình 2026-04-13 170702" src="https://github.com/user-attachments/assets/6d617b4f-86cb-4431-9610-7516f5e0efdb" />

> - khởi động dịch vụ SSH và cấu hình để SSH tự động chạy khi khởi động hệ thống. Sau đó, kiểm tra trạng thái dịch vụ và đảm bảo SSH hoạt động bình thường.

- truy cập SSH vào Ubuntu từ cmd của windows

BƯỚC 1: Lấy IP của Ubuntu Trong Ubuntu, gõ: ip -4 addr để xem ip của máy ubuntu
<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-13 092542" src="https://github.com/user-attachments/assets/6a9657ba-3131-4262-8abd-49a9f5dc701b" />

BƯỚC 2: Mở CMD trên Windows
gõ lệnh : ssh nonghonhat@ip_ubuntu
sau đó máy sẽ hỏi : Are you sure you want to continue connecting (yes/no/[fingerprint])?. chọn yes và sau đó nhập mật khẩu của ubuntu.
cấu hình SSH trên Ubuntu và sử dụng lệnh ssh từ máy Windows để kết nối đến máy Ubuntu thông qua địa chỉ IP. Sau khi nhập đúng thông tin đăng nhập, hệ thống hiển thị màn hình chào của Ubuntu, chứng tỏ kết nối SSH thành công.
<img width="1916" height="1073" alt="image" src="https://github.com/user-attachments/assets/5007bcdb-85db-4869-a1c2-134c485461b2" />

# 2. Tìm hiểu các lệnh cơ bản của ubuntu
- Liệt kê các file trong thư mục: ls
- Tạo thư mục: mkdir nameFolder
- Chuyển thư mục làm việc: cd path
- Copy file: cp file_nguồn path/file_đích
<img width="829" height="170" alt="Ảnh chụp màn hình 2026-04-13 105601" src="https://github.com/user-attachments/assets/64e4a944-b7e2-48c6-8ba5-d7ea9369425a" />
- Edit file: sudo nano tenfile
> - CTRL+o : lưu nội dung sau khi edit
> - CTRL+x : thoát edit file
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/081008e2-1400-440f-b6ac-43a08854de6f" />
- Thay đổi quyền thao tác file: sudo chmod xxx filename
<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-13 105956" src="https://github.com/user-attachments/assets/d669ba91-8f96-4c1c-9385-a34d2d84bc76" />
- Lệnh chmod 777 được sử dụng để cấp toàn quyền (đọc, ghi, thực thi) cho tất cả người dùng đối với file.
# 3. Cài đặt docker cho Ubuntu
# A. Cài Doker
- BƯỚC 1: Cập nhật hệ thống : sudo apt update
<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-13 110122" src="https://github.com/user-attachments/assets/f6db6a5f-d670-4a3c-9848-a37d5bd254f4" />
- BƯỚC 2: Cài Docker và kiểm tra phiên bản của docker : sudo apt install docker.io -y
<img width="1110" height="303" alt="Ảnh chụp màn hình 2026-04-13 211525" src="https://github.com/user-attachments/assets/a011548a-f5c8-4d9e-b386-8dda85fc7e6b" />
- BƯỚC 3:
> - Bật Docker : sudo systemctl start docker
> - Cho Docker tự chạy khi bật máy: sudo systemctl enable docker
BƯỚC 4 : Test Docker : sudo docker run hello-world

<img width="1353" height="761" alt="Ảnh chụp màn hình 2026-04-13 212212" src="https://github.com/user-attachments/assets/84db64c2-0d16-4fb6-b656-8cbcfb470115" />

=> đã cài đặt Docker trên Ubuntu bằng lệnh apt install docker.io, sau đó khởi động dịch vụ Docker và cấu hình để Docker tự động chạy khi khởi động hệ thống. Cuối cùng, kiểm tra bằng lệnh docker run hello-world và nhận được kết quả thành công.

B. Cài Docker Compose
Cài Docker Compose : sudo apt update sudo apt install docker-compose-v2 -y

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-13 110122" src="https://github.com/user-attachments/assets/2361402c-1b3d-4c94-8a6a-712438fd7b33" />

4. Kiểm tra phiên bản docker vừa cài đặt, kiểm tra phiên bản của docker compose
Kiểm tra Docker : docker --version

Kiểm tra Docker : docker --version
ảnh
Kiểm tra phiên bản Docker compose :
<img width="997" height="91" alt="Ảnh chụp màn hình 2026-04-13 213148" src="https://github.com/user-attachments/assets/89cb01d5-de08-4027-9b9c-9375917e69be" />
 5. Cấu hình để docker chạy mà không cần tiền tố sudo
 BƯỚC 1: Thêm user vào nhóm docker
sudo usermod -aG docker $USER
BƯỚC 2: Áp dụng thay đổi
newgrp docker
BƯỚC 3: TEST
docker run hello-world
KẾT QUẢ:
đã cấu hình để Docker có thể chạy mà không cần sử dụng sudo bằng cách thêm user vào nhóm docker và áp dụng thay đổi. Sau đó, kiểm tra và chạy container thành công mà không cần sudo.
<img width="1353" height="761" alt="Ảnh chụp màn hình 2026-04-13 212212" src="https://github.com/user-attachments/assets/7c83edd0-b372-4c33-a229-b9c97f9a1797" />
6. Tìm hiểu tập lệnh của docker và docker compose
A. Docker
Xem container đang chạy
docker ps
<img width="969" height="107" alt="Ảnh chụp màn hình 2026-04-13 212422" src="https://github.com/user-attachments/assets/f57e2539-8b7d-4b81-ba83-17e87c72f265" />
Xem tất cả container
docker ps -a
<img width="1903" height="155" alt="Ảnh chụp màn hình 2026-04-13 221534" src="https://github.com/user-attachments/assets/f22c0ce8-70a5-4edc-8a8b-e40d7cd7ab4f" />
Chạy container
docker run hello-world
<img width="1353" height="761" alt="Ảnh chụp màn hình 2026-04-13 212212" src="https://github.com/user-attachments/assets/b97782cf-a63b-4981-89f1-456b096a529c" />
Xóa container
docker rm ID_container
Xem image
docker images
