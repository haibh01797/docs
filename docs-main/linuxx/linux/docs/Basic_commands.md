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

- `snap` trong linux
- cài đặt gói bằng `snap install <tên gói>`
- xóa gói snap đã cài đặt `snap remove <tên gói>`
- lấy thông tin phiên bản của bất kỳ gói snap nào `snap list`
- cập nhật tất cả các gói đã cài đặt lên phiên bản mới nhất `snap refresh`
- `snap revert <tên gói>` lệnh này để quay lại phiên bản cũ 
- `snap list` để liệt kê tất cả các gói snap đã cài đtặ trong hệ thống 
- `snap find <tên gói>` để tìm kiếm các gói trong `snap store` 
- `snap info <tên gói>` để lấy thông tin về bất kỳ gói snap nào
- `snap changes <tên gói>` để hiển thị danh sách các thay đổi gần đây được thực hiện đối với 1 gói trên hệ thống 
- `snap login` để đăng nhập vào cửa hàng snap 
- `snap logout` để đăng xuất khỏi cửa hàng snap 
- `snap help ` để hiển thị các lệnh có sẵn của trình quản lý gói snap 
- `snap enable ` để kích hoạt các gói snap 
- `snap disable` để vô hiệu hóa 
- `snap connection` để hiển thị quyền được cấp cho 1 gói snap 

- `netstat` là 1 công cụ dòng lệnh để truy xuất số liệu thống kê mạng 
  - `-a` hiển thị tất cả các kết nối tcpvaf udp đang hoạt động và các cổng đang lắng nghe 
  - `-t` chỉ hiển thị các kết nối tcp
  - `-u` chỉ hiển thị các kết nối udp
  - `-l` chỉ hiển thị các socket đang lắng nghe tích cực các kết nối đến 
  - `-p` hiển thị PID và tên chương trình liên quan đến từng ổ cắm 
  - `-n` hiển thị địa chỉ và số cổng ở định dạng số mà không phân giải tên 
  - `-r` hiển thị bảng định tuyến kernel 
  - `-s` cung cấp số liệu thống kê tóm tắt cho từng giao thức 
  - `-c` cập nhật liên tục đầu ra mỗi giây 
  - `-e` hiển thin thông tin mở rộng bao gồm bộ đếm thời gian và id người dùng 

- `fdisk` thường dùng 
  - `n` tạo phân vùng 
  - `p` in bảng phân vùng 
  - `d` xóa 1 phân vùng 
  - `q` thoát mà không lưu thay đổi 
  - `w` ghi lại các thay đổi và thoát 

- `mount` trả về các giá trị sau đây cho biết trạng thái hoàn tất 
  - `0` thành công
  - `1` gọi lệnh không đúng hoặc không đủ quyền 
  - `2` lỗi hệ thống 
  - `4` lỗi gắn kết bên trong 
  - `8` hoạt động bị gián đoạn bởi người dùng 
  - `16` các vấn đề liên quan đến việc ghi hoặc xóa tệp /etc/mtab
  - `32` lỗi gắn kết 
  - `64` ít nhất một hoạt động gắn kết thành công , nhưng không phải tất cả 
- `mount` tùy chọn 
  - `-a` gắn kết tất cả các hệ thống tập tin được liên kết trong /etc/fstab
  - `-f` fork một phiên bản mới `mount` cho mỗi thiết bị . phải sử dụng kết hợp với `-a`
  - `-h` hiển thị tệp trợ giúp với tất cả các tùy chọn 
  - `-l` liệt kê tất cả các hệ thống tập tin đã gắn kết và thêm nhãn cho từng thiết bị 
  - `-L`[label] gắn kết vùng với đã chỉ định [label]
  - `-M` di chuyển một cây con đến 1 vị trí khác 
  - `-O` [opts] khi kết hợp với `-a` lệnh này sẽ giới hạn tập hợp hệ thống tệp được `-a` áp dụng . lệnh này [opts] đề cập đến các tùy chọn được chỉ định trong trường tùy chọn của tệp 
  `/etc/fstab` lệnh này chấp nhận nhiều tùy chọn được chỉ định trong danh sách phân cách bằng dấu phẩy 
  - `-r` gắn kết thống tập tin ở chế độ chỉ đọc 
  - `-R` gắn lại một cây con ở một vị trí khác , khiến nội dung của nó có sẵn ở cả hai 
  - `-t`[type] chỉ ra loại hệ thống tập tin
  - `-T` được sử dụng để chỉ định tệp `/etc/fstab`
  - `-v` gắn kết một cách chi tiết mô tả từng hoạt động 
  - `-V` hiển thị thông tin phiên bản chương trình
  

## shell
- `chmod +x tên file.sh` cấp quyền thực thi
- `./tên file.sh Ubuntu`chạy 
- các tùy chọn trong shell
- `-v`  bật chế độ chi tiết 
















