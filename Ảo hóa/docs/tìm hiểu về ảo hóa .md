# Ảo hóa 
## 1. ảo hóa là gì 
- là công nghệ tạo ra phiên bản ảo của tài nguyên máy tính , bao gôm máy chủ , hệ điều hành , thiết bị lưu trữ hoặc tài nguyên mạng . công nghệ này cho phép một máy vật lý duy nhất hoạt động như nhiều máy chủ ảo độc lập , giúp tối ưu hóa phần cứng 
## 2. cách thức hoạt động của ảo hóa 
- công nghệ ảo hóa hoạt động bằng cách tạo 1 lớp trừu tượng giữa phần cứng vật lý và các hệ điều hành hoặc ứng dụng chạy trên nó . lớp trừu tượng này do hypervisor cung cấp cho phép nhiều môi trường ảo cùng tồn tại và hoạt động song song trên một hệ thống vật lý 
- hypervisor là thành phần cốt lõi , là trái tim của mọi giải pháp ảo hóa . đay là một phần mềm có nhiệm vụ tạo chạy và quản lý các máy ảo . hypervisor cho phép hệ điều hành chủ hoặc trực tiếp phần cứng máy chủ lưu trữ nhiều hệ điều hành 
- có 2 loại hypervisor chính :
- hypervisor type 1 : loại này được cài đặt trực tiếp lên phần cứng của máy chủ giống như 1 hệ diều hành . chúng có quyền truy cập trực tiếp vào tài nguyên phần cứng mà không cần thông qua một hệ điều hành . giúp tăng cường tối ưu hiệu suất và tăng cường bảo mật 
- hypervisor type 2 : ngược lại chạy như một ứng dụng phần mềm trên hệ thống điều hành chủ đã được cài đặt sẵn . chúng phụ thuộc vào hệ điều hành chủ đề truy cập và quản lý tài nguyên phần cứng . điều này làm cho chúng dẽ cài đặt và sử dụng dẽ hơn
- máy ảo VM là 1 môi trường tính toán được phần mềm mô phỏng , hoạt động như một máy tính vật lý riêng biệt mỗi vm bao gồm tập hợp các tệp cấu hình xác định đặc tả phần cứng ảo của riêng mình ví dụ như cpu, dung lượng ram và kích thước ổ đĩa cứng ảo 
## 3. các loại ảo hóa phổ biến 
- ảo hóa máy chủ (server virtualization) là hình thức ảo hóa phổ biến nhất và có lẽ là quan trọng nhất . công nghệ này cho phép chia một máy chủ vật lý thành nhiều máy ảo độc lập . mỗi máy chủ ảo có thể chạy hệ điều hành và ứng dụng riêng hoạt động như 1 server chuyên dụng 
- lợi ích của ảo hóa máy chủ là khả năng hợp nhất server , giảm số lượng máy chủ vật lý cần thiết . điều này dẫn đến việc tiết kiệm đáng kể chi phí phần cứng , điện năng , không gian và chi phí quản lý đây cũng là công nhệ nền tảng của các dịch vụ vps(virtual private server)
- ảo hóa desktop (VDI) cho phép người dùng truy cập vào môi trường desktop của họ từ xa , từ bất kỳ thiết bị nào có kết nối mạng . thay vì chạy trên máy tính cá nhân , hệ điều hành desktop được lưu trữ và thực thi trên một máy chủ trung tâm 
- các loại ảo hóa khác: 
- ảo hóa mạng : công nghệ này cho phép tạo ra các mạng logic ảo hoàn toàn đọc lập trên một hạ tầng mạng vật lý chung . các tài nguyên mạng như sw, router, firewall có thể được ảo hóa , giúp tăng tính linh hoạt , bảo mật và đơn giản hóa việc quản lý mạng 
- ảo hóa lưu trữ : hình thức này gộp nhiều thiết bị lưu trữ vật lý từ các nhà cung cấp khác nhau thành một vùng lưu trữ duy nhất đucợ quản lý tập trung . điều này giúp tối ưu hóa việc sử dụng dung lượng , đơn giản hóa việc sao lưu phục hồi và di chuyển dữ liệu 
- ảo hóa ứng dụng : cho phép các ứng dụng chạy trong môi trường cô lập mà không cần cài đặt trực tiếp vào hệ điều hành của người dùng . ứng dụng được đóng gói và truyền trục tiếp đến thiết bị đầu cuối khi cần giúp giảm xung đột phần mềm và đơn giản hóa việc cập nhật , quản lý ứng dụng 
## 4 lợi ích 
- tối ưu hóa sử dụng tài nguyền phần cứng : đây là lợi ích rõ ràng nhất . ảo hóa cho phép một máy chủ vật lý chạy nhiều máy ảo , khai thác tối đa công suất cpu , bộ nhớ và lưu trữ 
- tiết kiệm chi phí đầu tư và vận hành : khi số lượng máy chủ vật lý giảm , chi phí mua sắm phần cứng ban đầu cũng giảm theo 
- tăng cường tính linh hoạt và khả năng mở rộng : việc tạo mới sao chép hoặc di chuyển máy ảo diễn ra máy nhanh chóng và dễ dàng 
- cải thiện khả năng khác phục sự cố và phục hồi sau thảm họa : máy ảo có thể dễ dàng được sao lưu toàn bộ dưới dạng tệp tin
- đơn giản hóa việc quản lý hạ tầng IT: các công cụ quản lý ảo hóa tập trung cho phép quản trị viên giám sát và điều kiện toàn môi trường ảo từ một giao diện duy nhất .
- tạo môi trường thử nghiệm và phát triển : lập trình viên và kỹ sư kiểm thử có thể nhanh chóng tạo ra các môi trường thử nghiệm cô lập đa dạng về cấu hình hệ điều hành và phần mềm 
- nâng cao tính bảo mật : sự cô lập giữa các máy ảo giúp ngăn chặn sự lây lan của phần mềm độc hại hoặc các vấn đề bảo mật từ một VM này sang VM khác . 
## 5 ứng dụng thực tế 
- data center / cloud : AWS , GCP , Azuze đều dựa trên ảo hóa 
- lab/test enviroment : dựng nhiều máy thử nghiệm trên laptop/server
- backup và disaster recovery: snapshot và migrate VM dễ dàng 
- devops : kết hợp với container và cicd pipelines
- security sandbox : kiểm thử malware , ứng dụng nguy hiểm trong môi trường tách biệt 

## 6 công nghệ và công cụ 
- ảo hóa toàn phần : VMware ESXI , KVM , hyper-V
- ảo hóa OS : docker , LXC , Podman 
- quản lý VM : proxmox VE , oVirt , Virt-manager
- ảo hóa lưu trữ : Ceph , GlusterFS, OpenEBS
- ảo hóa mạng : openvSwitch , VMware NSX 
- Cloud platform: openstack , cloudstack , vSphere

## 7. linux namespace 
- là 1 tính năng của linux cho phép ta tạo 1 virtualize system khá giống với chức năng của các công cụ virtual machine
- linux namespaces sẽ bao gồm các thành phần nhỏ hơn :
  - PID namespace cho phép ta tạo các process tách biệt 
  - networking namespace cho phép ta chạy chương trình trên bất kì port nào mà không bị xung đột với các process khác chạy trên server 
  - mount namespace cho phép ta mount và unmount filesystem mà không ảnh hưởng gì tới host filesystem 
## 8. Cgroups 
- là 1 tính năng của linux kernel cho phép quản trị viên hệ thống quản lý và giám sát tài nguyên hệ thống được sử dụng bởi nhóm tiến trình . tài nguyên bao gồm cpu , bộ nhớ , I/O đĩa và mạng 
- các chức năng 
- giới hạn tài nguyên : 
  - cpu : có thể giới hạn số lượng cpu mà một nhóm tiến trình có thể sử dụng 
  - bộ nhớ : bạn có thể giới hạn dung lượng bộ nhớ mà 1 nhóm tiến trình có thể sử dụng . nếu nhóm này sử dụng nhiều hơn dung lượng được phép hệ thống có thể giết các tiến trình để giải phóng bộ nhớ 
  - I/O đĩa : bạn có thể giới hạn tốc độ đọc ghi I/O của đĩa mà nhóm tiến trình có thể thực hiện
  - mạng : bạn có thể giới hạn băng thông mạng mà nhóm tiến trình có thể sử dụng 
- cách ly tài nguyên 
  - cgroups đảm bảo rằng tài nguyên của 1 nhóm tiến trình không bị ảnh hưởng bởi các nhóm tiến trình khác . điều này giúp duy trì hiệu suất ổn định cho các ứng dụng quan trọng
- giám sat tài nguyên 
 - cgroups cho phép giám sát việc sử dụng tài nguyên của các nhóm tiến trình bạn có thể kiểm tra dung lượng cpu , bộ nhớ , I/O đĩa các tiến trình đang sử dụng và đưa ra các diều chỉnh cần thiết 
 

