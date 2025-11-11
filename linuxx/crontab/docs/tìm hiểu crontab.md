# Crontab
## 1. Crontab là gì 
- crontab ( Cron table) là công cụ quản lý lịch trình tự động hệ điều hành linux , cho phép người dùng lên lịch các tác vụ dịnh kỳ và thực hiện chúng tự động mà không cần sự can thiệp thủ công .
- cron tab giúp bạn tạo và quản lý các tác vụ như chạy các script back up dữ liệu hay thực hiện các nhiệm vụ hệ thống vào những thời điểm xác định trước , như hàng ngày , hàng tuần hoặc vào một thời gian cụ thể 
## 2. các lưu ý đặc biệt 
- `,` dùng để đặt lịch cho nhiều thời điểm khác nhau 
- `/` dùng để dặt lịch chạy sau mỗi khoảng thời gian chỉ định
- `-` được sử dụng để đặt lịch chạy trong 1 khoảng thời gian nhất định 
- `@yearly` chạy mỗi năm 
- `@montly` chạy mỗi tháng 
- `@weekly` chạy mỗi tuần 
- `@daily` chạy mỗi ngày 
- `@houurly` chạy mỗi giờ 
- `@reboot` chạy sau khi khởi động lại hệ thống 
- ` crontab -e` tùy chọn cho phép tạo hoặc chỉnh sửa file crontab 
- `crontab -l` giúp hiện thị file crontab 
- `crontab -r ` cho phép xóa file crontab 
## 3 ứng dụng 
- lên task công việc : crontab giúp người dùng lên lịch tự động các tác vụ như sao lưu dữ liệu , quét virus hay thực hiện quy trình định kỳ vào thời gian cụ thể trong ngày , tuần , tháng hoặc năm 
- sao lưu dữ liệu : cron thường tự động tạo bản sao dữ liệu cơ sở dữ liệu , các file cấu hình quan trọng hoặc toàn bộ hệ thống hàng ngày , hàng tuần , hoặc hàng tháng , giúp đảm bảo an toàn cho dữ liệu 
- quản lý logs : các tác vụ cron đucợ thiết lập để tự động xóa các file log cũ , giúp tiết kiệm không gian lưu trữ và duy trì hệ thống 
- cấp nhập hệ thống : cron tự động hóa cập nhật phần mềm , hệ điều hành và các bản vá bảo mật giúp hệ thống luôn được bảo mật tối ưu 
- gửi email thông báo tự động : cron được sử dụng để gửi báo cáo , thông báo hoặc email nhắc nhở vào thời điểm cụ thể , như gửi cảnh báo hiệu suất hàng tuần cho quản lý 
- tự đọng hóa công việc lập trình : cron sẽ thực hiện các tác vụ liên quan đến lập trình chẳng hạn như xây dựng mã nguồn chạy các bài kiểm thử tự động và triển khai ứng dụng 
- quản lý dữ liệu : cron thực hiện các tác vụ như tối ưu hóa cơ sở dữ liệu , tái lập chỉ mục hoặc chạy các truy vấn sql định kỳ  
## 4 cài đặt crontab 
- `sudo apt update` 
- `sudo apt install cron`   

