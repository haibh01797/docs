# Tìm hiểu về Package management
### mục lục 

[1. khái niệm về quản lý package management ](#khainiem)

[2. cách cài đặt ](#caidat)

<a name="khainiem"></a>
## 1. khái niệm về quản lý package management

package management là 1 công cụ tự động hóa quá trình cài đặt cập nhật và gỡ bỏ các software package . nó cũng xử lý các phụ thuộc , đảm bảo rằng các thư viện và software package cần thiết được cài đặt để phần mềm hoạt động đúng cách 

các công cụ package management cung cấp 1 cách dễ dàng để quản lý phần mềm trong các bản phân phối linux đảm bảo hệ thống của bạn luôn cập nhật các phiên bản mới nhất 

có 2 loại gói cài đặt :
- Source code chưa được biên dịch nên khi sử dụng cần phải biên dịch để cho máy hiểu , cái này thường dùng cho lập trình viên nếu họ muốn đọc source code vọc vạch và đắp thêm
- file binary (.deb, .rpm ) file này đã được phân phối biên dịch và đóng gói cho user nên máy có thể hiểu được 

<a name="caidat"></a>
## 2. cách cài đặt 

| high level tool | low level tool | family |
|-----------------|----------------|--------|
|apt-get|dpkg|debian|
|zyper|rpm|SUSE|
|yum|rpm|Red hat|

### 2.1 quản lý gói debian và ubuntu 

 hệ thống quản lý goid debian dựa trên công cụ gọi là dpkg với hệ thống là 1 phiên bản hiệu quả , phổ biến và hữu ích của quản lý gói . ngoài debian 1 số bản phân phối nổi bật khác của GNU/Linux có nguồn gốc từ hệ thống debian nổi bật nhất là bản phân phối ubuntu
 - công cụ nâng cao gói (apt)

 lệnh apt-get được sử dụng tương tác với các gói của hệ điều hành (được chạy bởi quyền root)

 `apt-get install package-name` Cài đặt một gói phần mềm mới từ kho lưu trữ.

 `apt-get remove package-name` Gỡ bỏ gói phần mềm nhưng vẫn giữ lại cấu hình (config files) 

 `apt-get autoremove` Tự động gỡ các gói phụ thuộc không còn cần thiết (tức là các gói đã được cài làm phụ thuộc nhưng không còn được dùng nữa).  Dọn dẹp hệ thống, tiết kiệm dung lượng.

 `apt-get clean` Xoá toàn bộ cache của các gói .deb đã tải về nằm trong thư mục /var/cache/apt/archives . Giải phóng dung lượng ổ đĩa.

 `apt-get purge package-name` kết hợp các chức năng của loại bỏ và làm sạch cho một gói cụ thể , cũng như các file cầu hình

 `apt-get update` Cập nhật danh sách gói từ các kho lưu trữ. Không cài đặt hoặc cập nhật gói, chỉ lấy thông tin mới.chạy lệnh này trước khi cài phần mềm để đảm bảo danh sách gói là mới nhất.

 `apt-get upgrade` nâng cấp tất cả gói có bản cập nhật có sẵn . chạy lệnh này sau khi chạy lệnh apt-get update. Cập nhật hệ thống, giữ nguyên cấu trúc gói đã cài `

 lệnh apt-cache cung cấp thêm thông tin về gói 

  `apt-cache search package-name` Tìm kiếm các gói có tên hoặc mô tả .sẽ liệt kê các gói có tên hoặc mô tả liên quan. dùng khi không biết tên chính xác của gói mà chỉ biết 1 phần tên hoặc chức năng

  `apt-cache show package-name` hiển thị chi tiết thông tin về gói phần mềm gồm : tên đầy đủ , phiên bản , mô tả , phụ thuộc , maintainer(người quản lý gói) muốn biết rõ về 1 gói trước khi cài đặt

  `apt-cache depends package-name` hiển thị các gói phụ thuộc của gói phần mềm , muốn biết cài gói đó có kéo theo cài thêm gì không

  `apt-cache rdenends package-name` hiển thị các gói nào đang dùng hoặc phụ thuộc vào gói bạn đang tra cứu 

  `apt-cache pkgnames` liệt kê toàn bộ tên các gói phần mềm hiện có trong danh sách trong apt

 sử dụng dpkg 

 apt-get và apt-cache thường dễ sử dụng và kết nối đến các kho cho các công cụ quản lý gói cơ bản có tên dpkg và debconf . một số lệnh quan trọng 

 `dpkg -i package-file-name.deb` cài đặt 1 file.deb

 `dpkg --list search-pattern` liệt kê dach sách được cài trên hệ thống

`dpkg --configure package-name` cấu hình lại 1 gói đã được cài hoặc chưa cài đặt xong (dùng khi việc cài đặt bị gián đoạn , gói chưa được cấu hình hoàn chỉnh )

`dpkg -reconfigure package-name` thiết lập lại cấu hình cho gói đã cài 

### 2.2 quản lý package fedora và centos
 
- fedora và centos là các bản phân phối liên quan mật thiết đến nhau . sự khác biệt của chúng xuất phát từ cách gói được chọn để đưa vào kho .
- cả 2 hệ thống sử dụng YUM để tương tác với kho hệ thống và cài đặt phụ thuộc và cũng bao gồm một công cụ cấp thấp hơn được gọi là rpm cho phép tương tác với tường gói .
- công cụ YUM được phát triển cho hệ thống yellow dog linux như là 1 thay thế cho yup . yum là gói mặc định và kho lưu trữ công cụ quản lý cho 1 số hệ điều hành 

`yum install package-name` cài đặt 1 gói phần mềm và tự động xử lý các phụ thuộc cần thiết 

`yum remove package-name` gỡ bỏ phần mềm và các gói phụ thuộc không cần thiết 

`yum search search-pattenr` tìm kiếm các gói trong kho lưu trữ bằng tên mô tả có chứa từ khóa 

`yum deplist package-name` hiển thị các gói phụ thuộc cần thiết để cài đặt gói cụ thể

`yum check-update` kiểm tra các gói phần mềm có thể dược cập nhật

`yum info package-name` hiển thị thông tin chi tiết về 1 gói: tên phiên bản , môt tả , repo , kích thước, nhóm

`yum reinstall package-name` cài lại 1 gói đã cài đặt (nếu file lỗi /hỏng , cấu hình bị thay đổi mà muốn khôi phục bản mặc định)

`yum localinstall local-rpm-file` cài đặt gói từ file .rpm có săn trên máy , đồng thời tự động xử lý phụ thuộc nếu cần thiết 

`yum update optional-package-name` cập nhật gói cụ thể lên phiên bản mới nhất trong kho 

`yum upgare` cập nhật toàn bộ hệt thống như yum update nhưng cũng xử lý thay thế gói 

rpm cấc lệnh dưới đây được chạy dưới quyền user root

` rpm -ivh filename.rpm cài đặt 1 gói .rpm từ file đã tải về thủ công giống yum localinstall , nhưng không tự động xử lý phụ thuộc `
`i` install 
`v` verbose : chi tiết 
`h` hash 

`rpm -e package-name xóa gói khỏi phần mềm`

`rpm -qa liệt kê các gói đã cài đặt trên hệ thống `

`rpm -q kiểm tra xem 1 gói đã được cài đặt hay không`

`rpm -qi package-name hiển thị thông tin chi tiết : phiên bản mô tả , release , kiến trúc , thời gian build`

`rpm -ql package-name liệt kê toàn bộ file được cài bởi 1 gói`

`rpm -qf filename tìm xem 1 file bất kỳ trong hệ thống là thuộc về gói nào`











