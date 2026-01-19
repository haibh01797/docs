1. container 
- là phần mềm nền tảng cho phép container hoạt động trong hệ thống  máy chủ . container runtime chịu trách nhiệm cho mọi thứ từ việc lấy ảnh container từ sổ đăng ký container và quản lý vòng đời của chúng cho đến việc chạy container trên hệ thống 
- container runtime là công cụ chạy container  
- nó đảm bảo container
  - được tạo ra (create)
  - chạy (start)
  - dừng (stop)
  - xóa (delete)
  - quản lý filesystem mạng tài nguyên hệ thống liên quan
2. các lạo container runtime phổ biến 
- low - level runtiems 
  - `runc` runtime chuẩn OCI
  - `crun` runtime viết bằng C nhanh hơn runc
  - `gVisor` cung cấp sandbox an toàn hơn google 
  - `kata container` dùng lightweight vm để tăng bảo mật 
- high - level runtime
  - `containerd` được docker tách ra nay là runtime chuẩn của kubernetes
  - `CRI-O` runtime nhẹ cho kubernetes tương thích CRI
  - `docker Engine` gồm docker daemon + containerd + runc

