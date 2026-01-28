1. kubernets là gì 
- kubernets là 1 nền tảng để quản lý các container , chúng đóng gói mã nguồn , cấu hình và các phụ thuộc của 1 ứng dụng , cho phép ứng dụng đó chạy như 1 tiến trình độc lập với các tài nguyên riêng . mỗi ứng dụng có 1 container riêng hoặc nhiều container , được nhóm lại thành các pod kubernetes
- kubernetes có thể chạy trên máy chủ vật lý , máy ảo , nhà cung cấp dịch vụ đám mây công cộng , đám mây riêng và môi trường . kubernetes nó hoạt động trên nhiều loại cơ sở hạ tầng khác nhau 
- kubernetes được xây dựng để giúp người dùng tuân theo 3 nguyên tắc thiết kế cốt lõi . 1 hệ thống triển khai kubernetes cần phải :
  - bảo mật . nó phải tuân theo các chuẩn mực bảo mật mới nhất 
  - thân thiện với người dùng . có thể vân hành bằng 1 vài lệnh đơn giản 
  - có thể mở rộng . nó không nên ưu tiên 1 nhà cung cấp nào và nên được tùy chỉnh từ 1 tệp cấu hình 
2. lợi ích 
- hỗ trợ cho các môi trường lớn và phức tạp : 1 môi trường sản xuất chạy nhiều ứng dụng sẽ yêu cầu triển khai nhiều container trên nhiều máy chủ , tất cả cùng hoạt động với nhau . kubernetes cung cấp khả năng điều phối và quản lý cần thiết để triển khai container ở quy mô đáp ứng khối lượng công việc lớn 
- khả năng mở rộng : kubernetes tự động mở rộng quy mô dựa trên nhu cầu của bạn cung cấp dung lượng mà ứng dụng của bạn cần đồng thời tiết kiệm tài nguyên và chi phí 
- tính di động : kubernetes có thể chạy tại chỗ trong trung tâm dữ liệu của mình , trên đám mây công cộng và trong cấu hình lai giữa các phiên bản công cộng và riêng tư . với kubernetes , cùng 1 lệnh có thể được sử dụng ở bất cứ đâu 
- triển khai nhất quán : việc triển khai kubernetes nhất quán trên toàn bộ cơ sở hạ tầng . container thể hiện khái niệm về cơ sở hạ tầng bất biến , và tất cả các phụ thuộc cũng như hướng dẫn thiết lập cần thiết để chạy 1 ứng dụng đều được đóng gói cùng với container 
- phân tách và tự động hóa hoạt động và phát triển : container giúp tiết kiệm thời gian có các nhà phát triển , cho phép chu kỳ lặp lại nhanh chóng . đông thời kubernets giúp các nhóm vận hành tự tin về tính ổn định của hệ thống 
- hỗ trợ chiến lược đám mây : nhiều tổ chức kết hợp các trung tâm dữ liệu tại chỗ với các giải pháp đám mây công cộng hoặc riêng tư , và cân bằng khối lượng công việc giữa nhiều nhà cung cấp đám mây để tận dụng những thay đổi về giá cả và mức độ dịch vụ . tính nhất quán và khả năng di dộng của kubernetes có thể hỗ trợ các chiến lước 


