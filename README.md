# laptrinhweb_btvn3
Bài tập 3   : môn Phát triển ứng dụng trên nền web
Giảng viên  : Đỗ Duy Cốp
Lớp học phần: 58KTPM
Ngày giao   : 2025-10-24 13:50
Hạn nộp     : 2025-11-05 00:00
--------------------------------------------------
Yêu cầu     : LẬP TRÌNH ỨNG DỤNG WEB trên nền linux
1. Cài đặt môi trường linux: SV chọn 1 trong các phương án
 - enable wsl: cài đặt docker desktop
 - enable wsl: cài đặt ubuntu
 - sử dụng Hyper-V: cài đặt ubuntu
 - sử dụng VMware : cài đặt ubuntu
 - sử dụng Virtual Box: cài đặt ubuntu
2. Cài đặt Docker (nếu dùng docker desktop trên windows thì nó có ngay)
3. Sử dụng 1 file docker-compose.yml để cài đặt các docker container sau: 
   mariadb (3306), phpmyadmin (8080), nodered/node-red (1880), influxdb (8086), grafana/grafana (3000), nginx (80,443)
4. Lập trình web frontend+backend:
# Web thương mại điện tử
 - Tạo web dạng Single Page Application (SPA), chỉ gồm 1 file index.html, toàn bộ giao diện do javascript sinh động.
 - Có tính năng login, lưu phiên đăng nhập vào cookie và session
   Thông tin login lưu trong cơ sở dữ liệu của mariadb, được dev quản trị bằng phpmyadmin, yêu cầu sử dụng mã hoá khi gửi login.
   Chỉ cần login 1 lần, bao giờ logout thì mới phải login lại.
 - Có tính năng liệt kê các sản phẩm bán chạy ra trang chủ
 - Có tính năng liệt kê các nhóm sản phẩm
 - Có tính năng liệt kê sản phẩm theo nhóm
 - Có tính năng tìm kiếm sản phẩm
 - Có tính năng chọn sản phẩm (đưa sản phẩm vào giỏ hàng, thay đổi số lượng sản phẩm trong giỏ, cập nhật tổng tiền)
 - Có tính năng đặt hàng, nhập thông tin giao hàng => được 1 đơn hàng.
 - Có tính năng dành cho admin: Thống kê xem có bao nhiêu đơn hàng, call để xác nhận và cập nhật thông tin đơn hàng. chuyển cho bộ phận đóng gói, gửi bưu điện, cập nhật mã COD, tình trạng giao hàng, huỷ hàng,...
 - Có tính năng dành cho admin: biểu đồ thống kê số lượng mặt hàng bán được trong từng ngày. (sử dụng grafana)
 - backend: sử dụng nodered xử lý request gửi lên từ javascript, phản hồi về json.
5. Nginx làm web-server
 - Cấu hình nginx để chạy được website qua url http://fullname.com  (thay fullname bằng chuỗi ko dấu viết liền tên của bạn)
 - Cấu hình nginx để http://fullname.com/nodered truy cập vào nodered qua cổng 80, (dù nodered đang chạy ở port 1880)
 - Cấu hình nginx để http://fullname.com/grafana truy cập vào grafana qua cổng 80, (dù grafana đang chạy ở port 3000)
Yêu cầu sinh viên lưu code trên github
có file readme.md có hình ảnh + text: ghi lại nhật ký quá trình làm bài.
CÁCH ĐÁNH GIÁ:
1. Cài đặt được môi trường: 1đ
2. Cài đặt được các docker container với cấu hình phù hợp: 1đ
3. Web chạy được, giao diện phù hợp, chạy trên web sever nginx: 2đ
4. nodered api trả về json, test được: 2đ
5. front-end có js gọi được api nodered, nhận về json, hiển thị được kết quả từ json này. 2đ
6. Bài làm có dấu ấn, giải thích rõ ràng, hiểu vấn đề: 2đ
## BÀI LÀM
1. Cài đặt môi trường linux sử dụng VMware : cài đặt ubuntu
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/3d2933e1-764b-4c5b-adf3-de32da0afe4e" />
2.  Cài đặt Docker
<img width="940" height="527" alt="image" src="https://github.com/user-attachments/assets/a5d24db9-bb21-417d-b37f-47b0eac424a1" />
- Kiểm tra docker có hoạt động hay không:
<img width="940" height="651" alt="image" src="https://github.com/user-attachments/assets/663e189a-f3ad-48f3-ad11-e8cfeeded5ce" />
3. Sử dụng 1 file docker-compose.yml để cài đặt các docker container sau:
- Tạo file ocker-compose.yml:
 <img width="940" height="669" alt="image" src="https://github.com/user-attachments/assets/f99662d9-e9e3-4320-9443-79a3b3a8570f" />
 - cài đặt các docker container mariadb (3306), phpmyadmin (8080), nodered/node-red (1880), influxdb (8086), grafana/grafana (3000), nginx (80,443):
<img width="940" height="903" alt="image" src="https://github.com/user-attachments/assets/07f5d982-369c-4aa2-87f9-ca62d262f7e4" />
4. Lập trình web frontend+backend:
- Tạo cơ sở dữ liệu trong phpMyAdmin:
<img width="940" height="852" alt="image" src="https://github.com/user-attachments/assets/d2bee6c7-47ff-4cbe-848e-dedd9905bc79" />
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/2f69548b-3562-45f5-8133-9a227b7d7e47" />
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/b4d2985e-53fb-4a25-afc0-b33253a231fe" />
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/9e3c1a88-57be-4bc9-a26a-f23987404adb" />
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/c9166c5e-4da8-4dba-b2e8-6933690c00c1" />
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/23dd26e4-619b-4ae3-949e-f77c5d0d7af9" />
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/36c0f220-c225-41ca-9854-7b11dc89f5d1" />
- Nodered:
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/8bbd57ca-927c-4591-becb-f497d853fa56" />
- truy cập http://localhost:1880/get-users :
<img width="940" height="716" alt="image" src="https://github.com/user-attachments/assets/c88f591f-05bd-4b28-81df-7af25ce74a50" />
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/4482f5f9-f899-4876-9a64-62751fcd2835" />
-
-
-
-
-
-
-
-
-
-
-
-
-
-
5. Nginx làm web-server
- Cấu hình nginx để chạy được website qua url http://fullname.com
<img width="940" height="1056" alt="image" src="https://github.com/user-attachments/assets/f777ffb4-254e-44ed-a8dd-b5f38aa0811a" />











