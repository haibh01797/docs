# Tổng quan về Zabbix
1. Zabbix là một nền công cụ giám sát mã nguồn mở mạnh mẽ dùng để theo dõi và cảnh báo tình trạng của hệ thống . zabbix giúp phát hiện sớm sự cố , gửi cảnh báo và hiển thị dashbroad thống kê thời gian thực 
2. cách hoạt động của zabbix 
- agent thu thập dữ liệu ( cpu , ram,http status code)
- zabbix server nhận dữ liệu ghi vào db
- trigger kiểm tra điều kiện (cpu , status )
- nếu điều kiện đúng -> tạo event -> kích hoạt action
- action gửi thông báo 
- frontend hiển thị dữ liệu dạng biểu đồ , dashbroad
2. các khái niệm cơ bản trong zabbix 
- host thiết bị hoặc máy chủ cần giám sát 
- item một chỉ số cụ thể (cpu, disk, http status)
- trigger biểu thức logic xác định khi nào xảy ra sự cố 
- event sự kiện được tạo khi trigger kích hoạt 
- action hành động thực hiện khi có event 
- template tập hợp item+trigger+graph giúp áp dụng nhanh cho nhiều host
- dashbroad hiện thị dữ liệu dạng biểu đồ hoặc bảng điều khiển tông hợp 
- discovery tự động phát hiện thiết bị service hoặc filesystem để giám sát 
3. ưu điểm 
- giám sát server và thiết bị mạng 
- dễ dàng thao tác và cấu hình 
- đáng tin cậy trong việc chứng thực người dùng 
- linh hoạt trong việc phân quyền người dùng 
- mã nguồn mở 
4. các thành phần của zabbix 
- zabbix server đây là thành phần trung tâm của phần mềm zabbix . zabbix server có thể kiểm tra các máy chủ từ xa thông qua các báo cáo của agent gửi về cho zabbix server và từ đó nó sẽ lưu trữ tất cả các cấu hình cũng như là các số liệu thông kê
- database strorage tất cả thông tin cấu hình cũng như dữ liệu được zabbix thu nhập được lưu trữ trong cơ sở dữ liệu 
- zabbix proxy là phần tùy chọn của zabbix nó có nhiệm vụ thu nhận dữ liệu trong bộ nhớ đệm và chuyển đến zabbix server 
- zabbix agent để giám sát chủ động các thết bị cục bộ và các ứng dụng (ổ cứng bộ nhớ ) trên hệt hống mạng . zabbix agent sẽ được cài lên trên server và từ đó agent sẽ thu nhập thông tin hoạt động từ server mà nó đang chạy và báo cáo dữ liệu này đến zabbix server để xử lý 
- web interface được cung cấp để dễ dàng truy cập zabbix từ mọi nơi và mọi nền tảng . web interface thường chạy trên cùng 1 máy vật lý với zabbix server
 