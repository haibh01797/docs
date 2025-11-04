# LVM
## 1. LVM là gì 
- là một cơ chế cung cấp một phương pháp quản lý hệ thống lưu trữ thay thế cho phương pháp phân vùng truyền thống . trong LVM , thay vì tạo phân vùng , bạn tạo các ổ đĩa logic sau đó bạn có thể dễ dàng gắn các ổ đĩa đó vào hệ thống tệp của mình như cách gắn 1 ổ đĩa phân vùng 
## 2. các thành phần của LVM
- LVM có ba thành phần chính 
  - khối lượng vật lý 
  - nhóm khối lượng 
  - khối lượng logic
## 3.Ưu điểm của LVM 
 - việc thay đổi kích thước một ổ đĩa logic hoặc nhóm ổ đĩa rất dễ dàng . nó loại bỏ tất cả các phần không cần thiết (phân vùng , đĩa thô) và để lại cho chúng ta 1 nhóm lưu trữ trung tâm để làm việc 
## 4 cơ chế LVM 
- một hoặc nhiều đĩa cứng hoặc phân vùng được định cấu hình physical volume (PV)
- một volume group (VG) được tạo bằng cách sử dụng một hoặc nhiều khối vật lý 
- nhiều logical volume có thể được tạo trong một volume group 

 
