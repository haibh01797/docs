# 1 tìm hiểu về ICMP 
1. ICMP là gì 
- là giao thức tiện ích của tcp/ip chịu trách nhiệm cung cấp thông tin về tính khả dụng của các thiết bị , dịch vụ hoặc tuyến đường trên mạng TCP/IP
- mục đích cảu việc ping ICMP là kiểm tra giao tiếp giao tiếp giữa các thiết bị . dữ liệu được gửi từ máy chủ này đến máy chủ khác dưới dạng yêu cầu và máy chủ nhận dữ liệu phải gửi lại dữ liệu dó dưới dạng phản hồi
- cấu trúc gói tin ICMP cơ bản :
- `Type` xác định loại thông báo ICMP
- `code` cung cấp thông tin chi tiết hơn về nguyên nhân hoặc mục đích của thông báo , chẳng hạn như xử lý gói tin không đến được đích 
- `checksum` giúp kiểm tra tính toàn vẹn của gói tin , phát hiện lỗi trong quá trình truyền 
- phần dữ liệu chứa thông tin bổ sung , thường bao gồm phần header và dữ liệu của gói ip ban đầu gây lỗi , để thiết bị dích có thể phân tích và xử lý 

 - `-c` chỉ định số lượng gói tin cần gửi 
 - `-i` đặt khoảng thời gian giữa các lần truyền gói tin 
 - `-f` gửi gói tin nhanh nhất có thể 
 - `-t` đặt giới hạn số lần chuyển mạng 
 - `-s` điều chỉnh kích thước của gói tin ping theo byte.
 - `-p` Xác định số lượng gói tin được gửi trong mỗi đợt.
 - `-W`Đặt thời gian tối đa để chờ phản hồi.
 - `-w`Chỉ định tổng thời gian giới hạn cho pinghoạt động.
 - `-q` Chế độ im lặng: ngăn chặn âm thanh chi tiết.

 2. traceroute 
 - `-w` cấu hình thời gian chờ 
 - `-q` thay đổi số lượng gói tin đã gửi và nhận 
 - `-m` chỉ định số bước nhảy
 - `-f` chỉ định TTL nào sẽ bắt đầu 
 - `-s` thêm địa chỉ nguồn thay thay thế để theo dõi định tuyến 
 - `-n` vô hiệu hóa ánh xạ tên máy chủ thành địa chỉ ip 
 - `-g` định tuyến các gói thoogn qua cổng 
 - `-p` thay đổi cổng đích 
 - `-F` vô hiệu hóa phân mảnh gói tin



 3. netstat
 - là một trong những tiện ích phổ biến nhất để theo dõi các kết nối trên mạng của bạn 

 - `-l` tìm tất cả các cổng lắng nghe 
 - `-a` liệt kê các cổng đang nghe và không nghe 
 - `lt` tìm cổng lắng nghe tcp
 - `-lu` tìm cổng lắng nghe udp
 - `-at` liệt kê tất cả các kết nối cổng tcp
 - `-au` liệt kê tất cả các kết nối udp
 - `-s` nhận bản tóm tắt thống kê giao thức 
 - `-st` nhận số liệu thống kê cho một kết nối cụ thể 
 - `-s --raw` nhận số liệu thống kê mạng thô 
 - `-p` tìm dịch vụ có PID
 - `-i` hiển thị các giao dịch của giao diện mạng 
 - `-c` giám sát mạng liên tục bằng lệnh netstat 
- các cột internet hoạt động
 - `proto` giao thức được socket này sử dụng 
 - `Recv-Q` hàng đợi nhận đây là các byte đến đã được nhận và được lưu vào bộ đệm chờ tiến trình cục bộ đang sử dụng kết nối 
 - `send -Q` hàng đợi gửi hiển thị các byte đã sẵn sàng để gửi từ hàng đợi gửi 
 - `Local Address` chi tiết địa chỉ của đầu cuối cục bộ kết nối 
 - `Foreign address` địa chỉ và số cổng của đầu xa kết nối 
 - `state` trạng thái của socket 

 - đối với kết nối tcp giá trị trang thái có thể là một trong những giá trị sau
 - `listen` chỉ ở phía máy chủ . socket đang chờ yêu cầu kết nối 
 - `SYN-SENT` chỉ ở máy khách . socket này đã gửi yêu cầu kết nối và đang chờ xem có được chấp nhận hay ko
 -  `SYN-RECEIVED` chỉ dành cho phía máy chủ . socket này đang chờ xác nhận kết nối sau khi chấp nhận yêu cầu kết nối 
 - `ESTABLISHED` máy chủ và máy khách . một kết nối hoạt động đã được thiết lập giũa máy chủ và máy khách cho phép truyền dữ liệu giữa hai máy 
 - `FIN-WAIT-1` máy chủ và máy khách socket này đang chờ yêu cầu chấm dứt kết nối từ socket từ xa hoặc xác nhận yêu cầu chấm dứt kết nối đã được gửi trước đó từ socket này 
 - `FIN-WAIT-2` máy chủ và máy khách socket này đang chờ yêu cầu chấm dứt kết nối từ socket từ xa 
 - `CLOSE-WAIT` máy chủ và máy khách socket này đang đang chờ yêu cầu chấm dứt kết nối từ người dùng cục bộ 
 - `CLOSING` máy chủ và máy khách . socket này đang chờ xác nhận yêu cầu chấm dứt kết  nối từ socket từ xa
 - `LAST-ACK` máy chủ và máy khách . socket này đang chờ xác nhận yêu cầu chấm dứt kết nối mà nó đã gửi đến socket từ xa 
 - `TIME-WAIT` máy chủ và máy khách . socket này đã gửi một xác  nhận đến socket từ xa để thông báo rằng nó đã nhận yêu cầu kết thúc của socket từ xa . hiện tại socket đang chờ để đảm bảo rằng xác nhận đã được nhận 
 - `CLOSED` không có kết nối do đó ổ cắm bị chấm dứt  
 - các cột "miền unix"
 - `proto` giao thức này được socket sử dụng 
 - `refcnt` sood lượng tham chiếu . số lượng tiến trình được kết nối với socket
 - `flags` thông thường được đặt thành ACC nghĩa là ổ cắm đang chờ yêu cầu kết nối 
 - `type` loại ổ cắm 
 - `state` trang thái của socket 
 - `I-node` inode của hệ thống tập tin được liên kết với ổ cắm này 
 - `path` đường dẫn hệ thống tệp đén ổ cắm 
 - `DGRAM` socket được sử dụng  các thông điệp có độ dài cố định . datagram không được đảm bảo là đáng tin cậy được sắp xếp theo trình tự 
 - `STEAM` socket này là luồng . các kết nối này đucợ thiết kế để cung cấp khả năng truyền tải gói tin theo trình tự 
 - `RAW` socket này đang sử dụng như 1 socket thô . socket thô hoạt động ở cấp độ mạng và không tham chiếu đến các tiêu đề tcp và udp từ cấp độ vận chuyển 
 - `RDM` ổ cắm này nằm ở 1 đầu kết nối tin nhắn được truyền tải một cách đáng tin cậy 
 - `SEQPAKET` socket này hoạt động như một socket gói tuần tự 
 - `packet` ổ cắm truy cập giao diện thô 

4. packet analysis
- tìm hiểu về lưu lượng mạng : bao gồm việc giám sát và kiểm tra các gói dữ liệu đi qua mạng . quá trình này rất quan trọng vì nhiều lý do như đảm bảo an ninh mạng , xử lý sự cố mạng và tối ưu hóa hiệu suất mạng . các công cụ như tcpdump và wireshark giúp quản lý nhiệm vụ này dễ dàng hơn bằng cách cung cấp thông tin chi tiết về hoạt động bên trong mạng 
- bắt đầu với tcpdump :
  - tcpdump là một trình phân tích gói tin dòng lệnh mạnh mẽ trên linux . nó cho phép người dùng nắm bắt và hiển thị tcp/ip và các gói khác đang được truyền hoặc nhận qua mạng máy tính được kết nối
- kỹ thuật tcpdump 
 - thu nhập và lưu dữ liệu vào tệp để phân tích 
 - đọc từ một tập tin gói tin đã lưu 
 - kết hợp nhiều bộ lọc để thu nhập dữ liệu chính xác 
- wireshask cung cấp giao diện đồ họa thân thiện với người dùng giúp việc diễn giải dữ liệu dễ dàng hơn 
- các tính năng nâng cao wireshask 
  - giải mã và phân tích nhiều giao thức khác nhau 
  - xây dưng lại luồng lưu lượng truy cập , chẳng hạn như phiện hoặc lượt tải xuống 
  - hiển thị gói hàng theo mã màu để dễ nhận biết 
- ứng dụng thực tế 
 - phân tích bảo mật xác định các hoạt động đáng ngờ và các lỗ hổng vảo mật tiềm ẩn 
 - khác phục sự cố mạng chẩn đoán sự cố và tình trạng tắc nghẽn mạng 
 - mục đích giáo dục tìm hiểu về giao thức mạng và mô hình lưu lượng 
 
