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

