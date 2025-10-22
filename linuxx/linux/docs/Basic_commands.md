# 1. Linux 
## 2. Basic commands 

- `pwd` dùng để hiển thị thư mục mà mình đang ở 
- `ls` dùng để hiển thị tất cả các tệp và thư mục trong thư mục hiện tại 
- `cd` dùng để điều hướng từ thư mục này sang thư mục khác 
- `mv` dùng để đi chuyển hoặc đổi tên tệp và thư mục 
- `/` thư mục gốc cấp cao nhất của hệ thống tập tin 
- `/home` chưa dữ liệu người dùng và các tệp cấu hình dành riêng cho người dùng 
- `/bin` chứa các tệp thực thi của nhiều lệnh shell cơ bản như ls , cp , cd 
- `/sbin` chứa tệp nhị phân chỉ có thể được chạy bởi root hoặc người dùng sudo
- `/etc` chứa các tệp cấu hình cốt lõi của hệ thống 
- `/var` là nơi các chương trình lưu trữ thông tin thời gian chạy như ghi nhật ký hệ thống , theo dõi người dùng , bộ nhớ đệm và các tệp khác mà chương trình hệ thống tạo và quản lý 
- `/usr` chứa tất cả các tệp thực thi , thư viện , mã nguồn của hầu hết các chương trình hệ thống 
- `/lib` chứa các thư viện cần thiết cho các tệp nhị phân trong thư mục /bin và /sbin
- `/tmp` tệp tạm thời  
- `/dev` thư mục này chỉ chứa các các tệp liên quan đến thiết bị 
- `/dev/null` có thể được gửi để hủy bất kỳ tệp hoặc chuỗi nào 
- `/dev/zero` chứa chuỗi vô hạn 0
- `/dev/ramdom` chứa 1 chuỗi vô hạn các giá trị ngẫu nhiên 
- `/boot` chứa các tập tin của kernel và ảnh khỏi động  cùng với LILO và GRUB
- `/proc` chứa thông tin về các tiến trình đang chạy và các tham số kernel
- `ll` dùng để hiển thị tất cả các tệp và thư mục trong thư mục hiện tại chi tiết 
- `mkdir <tên thư mục>` tạo thư mục mới 
- `touch <tên tập tin>` tạo tập tin mới 
- `rm <tên tập tin>` xóa tập tin
- `rm <tên tập tin> <tên tập tin>` xóa nhiều tập tin
- `rm /h/a/i <tên tập tin>` xóa tập tin theo đường dẫn 
- `rm -i` xóa  cần xác nhận 
- `rm -f` xóa không cần xác nhận 
- `cat` và `tail` mở tập tin
- `vi <tên file>` để soạn văn bản 
- `tar` các options 
- `-c` tạo file để nén 
- `-x` giải nén 
- `-v` hiển thị quá trình nén và giải nén dữ liệu ra màn hình 
- `-f` chỉ định nén thành file 
- `--wildcards` tìm và xuất file bất kỳ trong file nén 
## 2 tiến trình 
- `top` lệnh này được sử dụng để hiển thị tất cả các tiến trình trong linux đang diễn ra môi trường làm việc của linux 
- `bg` lệnh này điều khiển công việc giúp tiếp tục công việc đã dừng trong khi vẫn giữ công việc đó chạy ở chế độ nền 
- `fg` lệnh này điều khiển công việc giúp tiếp tục công việc đã dừng trong khi vẫn giữ công việc đo chạy ở chế độ trước 
- `ps` lệnh này hiển thị thông tin về các tiến trình đang chạy 
 - ` ps aux` hiển thị tất cả tiến trình trên hệ thống 
 - `ps -f` cung cấp các thông tin đầy đủ của tiến trình
 - `UID` id người dùng của chủ sở hữu tiến trình 
 - `PID` id tiến trình là mã định danh duy nhất được gán cho mỗi tiến trình đang hoạt động
 - `PPID` id tiến trình cha hoặc ID của tiến trình đã bắt đầu của tiến trình hiện tại 
 - `c` mức độ sử dụng cpu của tiến trình 
 - `STIME` thời gian bắt đầu quá trình 
 - `TTY` thiết bị đầu cuối liên quan đến quy trình 
 - `time` thời gian cpu được quy trình sử dụng 
- ` nice` lệnh này được dùng để bắt đầu 1 tến trình mới trong khi chỉ định giá trị ưu tiên . giá trị nằm trong khoảng -20 > 19 . -20 là mức ưu tiên cao nhất 
- `kill` lệnh này được sử dụng để kết thúc các tiến trình linux hoặc truyền tín hiệu đến chúng . bạn có thể dừng 1 tiến tình 1 cách nhẹ nhàng hoặc ép buộc bằng cách chỉ định id `pid`
- `df` hiển thị dung lượng đĩa trống (ổ cứng ) trên tất cả các hệ thống tệp 
- `free` hiển thị tổng dung lượng bộ nhớ trống và đã sử dụng (Ram) trên hệ thống

- `proc` là 1 hệ thống giả lập tập tin nó cung cấp thông tin về hệ thống , tiến trình và kernel theo thời gian thực 
  - kiểm tra trạng thái hệ thống 
  - xem thông tin về tiến trình (process)
  - truy xuất thông tin kernel mà không cần dùng lệnh đặc biệt 
  - tương tác với kernel trong 1 số trường hợp 
  - mỗi tiến trình đang chạy sẽ có 1 thư mục con trong `/proc` với tên `PID` 















