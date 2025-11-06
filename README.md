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
1. enable wsl: cài đặt ubuntu
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/3941fb37-16d9-45a7-8cb5-113e7e41e68c" />
bật WSL và cài Ubuntu thành công
<img width="940" height="483" alt="image" src="https://github.com/user-attachments/assets/a24e5e8b-aebb-44e7-a169-ae354df6ad11" />
Kiểm tra docker có hoạt động hay không
<img width="940" height="653" alt="image" src="https://github.com/user-attachments/assets/5a3546f7-1793-4f94-af02-0f9ebe6e6208" />
Sử dụng 1 file docker-compose.yml để cài đặt các docker container sau: 
   mariadb (3306), phpmyadmin (8080), nodered/node-red (1880), influxdb (8086),
<img width="940" height="486" alt="image" src="https://github.com/user-attachments/assets/028f33df-3dc7-4e35-91e4-afd824024d59" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8f85536f-95cf-4da1-a3da-1b0a596b9d87" />
Cấu hình latest_values
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/1139a915-06d3-4015-90ca-534a947569aa" />
<img width="940" height="126" alt="image" src="https://github.com/user-attachments/assets/e10323c9-374b-4af8-b588-e5cfdceced89" />
Kết quả:
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/bd40d964-1d66-4578-b024-54996cd695b0" />
Cấu hình user
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/44512e56-7f8b-44b0-bd54-2adbb1e2fb04" />
<img width="940" height="156" alt="image" src="https://github.com/user-attachments/assets/3f801c36-b8ea-4eda-a07c-780857aa1e5f" />
Cấu hình sessions
<img width="1898" height="1078" alt="image" src="https://github.com/user-attachments/assets/4a11a3a7-c09b-47d2-bbad-19afc6843ff1" />
<img width="1142" height="275" alt="image" src="https://github.com/user-attachments/assets/cbdaa50d-3cdb-4338-af00-91ea4362c1e3" />
- Kết Quả:
<img width="934" height="170" alt="image" src="https://github.com/user-attachments/assets/ba616c0f-7aa6-4e38-8e99-30a8f539d240" />
5 Nginx làm web-server
 - Cấu hình nginx để chạy được website qua url http://fullname.com  (thay fullname bằng chuỗi ko dấu viết liền tên của bạn)
 - Cấu hình nginx để http://fullname.com/nodered truy cập vào nodered qua cổng 80, (dù nodered đang chạy ở port 1880)
 - Cấu hình nginx để http://fullname.com/grafana truy cập vào grafana qua cổng 80, (dù grafana đang chạy ở port 3000)


<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/cad3b153-70b5-4873-962c-c90a09d0d91a" />
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/fecfb984-cf34-4c6a-8c0a-5577912a60c7" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/672adc60-71c2-43be-aac8-1c1abf7a19b0" />
## Kết Luận
Trong quá trình thực hiện bài tập, em đã nắm vững quy trình **cài đặt hệ điều hành Ubuntu trên máy ảo VMware** và triển khai thành công các dịch vụ **MariaDB, phpMyAdmin, Node-RED, InfluxDB, Grafana và Nginx** thông qua **Docker Compose**.
Hệ thống web được xây dựng theo mô hình **Single Page Application (SPA)** cho phép người dùng **đăng nhập, theo dõi dữ liệu cảm biến theo thời gian thực**, đồng thời **xem biểu đồ lịch sử** được hiển thị trực quan qua **Grafana**. **Node-RED** đảm nhận vai trò **xử lý và lưu trữ dữ liệu cảm biến**, trong khi **Nginx** được cấu hình làm **máy chủ web trung tâm**, giúp hợp nhất việc truy cập các dịch vụ thông qua tên miền tùy chỉnh.

Bài làm đã giúp em **hiểu rõ quy trình tích hợp và vận hành một hệ thống IoT hoàn chỉnh**, từ khâu thu thập, lưu trữ đến trực quan hóa dữ liệu. Đồng thời, em cũng **rèn luyện được kỹ năng triển khai thực tế với Docker, Nginx và các công cụ giám sát**, góp phần củng cố tư duy hệ thống và khả năng ứng dụng công nghệ vào các dự án web – IoT trong tương lai.











