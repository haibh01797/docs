# NGINX 
## 1. NGINX là gì 
 nginx là 1 phần mềm máy chủ http và reverse proxy ngoài ra nó còn là load balancer và http cache 

 ## 2. tính năng chính của nginx
- web server: giống apache phục vụ các file tĩnh (.html, .css .js) rất nhanh hiệu quả nhờ kiến trúc event-driven 
- revrse proxy : đứng giữa client và ứng dụng , nhận request chuyển  đến ứng dụng backend xử lý -> nhận response và trả lại client 
- load balancer : khi có nhiều server backend NGINX có thể chia đều request để giảm tải 
- hộ trợ cache : lưu nội dung response vào bộ nhớ để phục vụ nhanh hơn 
- hộ trợ SSL/TLS : cấu hình https dễ dàng , thường dùng với let's encrypt để có ssl miễn phí 
## 3. NGINX hoạt đọng như thế nào 
- nginx sử dụng mộ hình sự kiện bất đồng bộ cho phép xử lý hàng ngàn kết nối đồng thời bằng rất ít tài nguyên 
- có 1 hoặc vài tiến trình chính xử lý tất cả kết nối bằng cách lắng nghe sự kiện 
- khi một request gửi đến : 
 - Nginx đăng ký xử lý request dó như một sự kiện 
 - nếu request cần chờ (để đọc dữ liệu từ disk/backend) , nginx không chặn mà tiếp tục xử lý các request khác 
 - khi dữ liệu sẵn sàng ngĩn nhận thông báo và tiếp tục xử lý phần còn lại 
- nhờ đó 1 tiến trình có thể xử lý hàng nghìn kết nối cùng lúc mà không tốn nhiều tài nguyên 
