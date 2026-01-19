# Tìm hiểu về SQL 
## 1. SQL là gì
- sql là ngôn ngữ truy vấn có cấu trúc , dùng để làm việc với cở sở dữ liệu quan hệ 
## 2. SQL có thể làm gì 
- SQL có thể thực hiện các truy vấn đối với cở sở dữ liệu 
- SQL có thể truy xuất dữ liệu từ cơ sở dữ liệu 
- SQL có thể chèn bản ghi vào cơ sở dữ liệu 
- SQL có thể cập nhật các bản ghi trong cở sở dữ liệu 
- SQL có thể xóa bản các bản ghi khỏi cở sở dữ liệu
- SQL có thể tạo cở sở dữ liệu mới 
- SQL có thể tạo các bảng mới trong cơ sở dữ liệu 
- SQL có thể tạo các thủ tục được lưu trữ trong cơ sở dữ liệu
- SQL có thể tạo chế độ xem trong cơ sở dữ liệu 
- SQL có thể thiết lập quyền trên các bảng thủ tục và chế độ xem 
## 3. mysql là gì 
- mysql là 1 hệ quản trị cơ sở dữ liệu quan hệ mã nguồn mở dùng SQL làm ngôn ngữ chính để thao tác dữ liệu 
1. mysql server là 1 máy tính hoặc hệ thống gồm nhiều máy tính được cài đặt phần mềm mysql nhằm mục đích lưu trữ dữ liệu , cho phép các máy khách kết nối để quản lý và truy xuất thông tin.
2. mysql client là thuật ngữ dùng để chỉ bất kỳ phần mềm nào có thể gửi truy vấn đến mysql server và nhận kết quả trả về 
## 4. MySQL dùng để làm gì 
- quản lý nội dung website : lưu trữ bài viết , bình luận , thông tin , người dùng có các hệ thống quản lý nội dung
- xây dưng Ứng dúng web và di động : lưu trữ thông tin người dùng , lịch sử giao dịch , dữ liệu sản phẩm có các nền tảng thương mại điện tử , mạng xã hội và các ứng dụng
## 5. syntax SQL 
`SELECT` trích xuất dữ liệu từ cơ sở dữ liệu 
`UPDATE` cập nhật dữ liệu trong cở sở dữ liệu
`DELETE` xóa dữ liệu khỏi cơ sở dữ liệu 
`INSERT INTO` chèn dữ liệu mới vào cơ sở dữ liệu 
`CREATE DATABASE` tạo 1 cơ sở dữ liệu mới 
`ALTER DATABASE` sửa đổi cơ sở dữ liệu 
`CREATE TABLE` tạo một bảng mới 
`ALTER TABLE` sửa đổi 1 bảng 
`DROP TABLE` xóa 1 bảng 
- 1 số quyền có thể gán cho user trong databse
- ` ALL PRIVILEGES` cho phép user thực hiện toàn quyền trên database 
- `CREATE` cho phép user tạo mới tables hoặc database 
- `DROP` cho phép xóa tables hoặc database 
- `DELETE` cho phép xóa bản ghi dữ liệu trong bảng tables 
- ` INSERT` cho phép thêm bản ghi mới vào bảng database
- ` UPDATE` cho phép cập nhật database
- ` GRANT OPTION` cho phép gán hoặc xóa quyền của người dùng khác 
- `REVOKE` lệnh này thu hồi quyền của user 
- `FLUSH PRIVILEGES` lệnh này để áp dụng thay đổi quyền 



