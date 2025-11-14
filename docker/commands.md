# docker 
- docker là một công cụ giúp ta tương tác với công nghệ container ở bên dưới , chứ nó không phải là container . đúng hơn docker là một tool giúp ta tương tác với container một cách dễ dàng thay vì ta phải làm nhiều thứ . và docker sẽ tương tác với container bên dưới thông qua container runtime 
- container là 1 công nghệ cho phép các ứng dụng được đóng gói và cô lập với toàn bộ môi trường chạy thực tế của chúng . diều này giúp dễ dàng duy trì nhất quán trong khi di chuyển ứng dụng được chứa giữa các môi trường (phát triển , thử nghiệm sản xuất ) và trên các nên tảng đám mây công cộng , riêng tư , lai và tại chỗ . nhờ tính nhẹ và di động , container mang đến cơ hội phát triển nhanh hơn và đáp ứng các nhu cầu kinh doanh ngay khi chúng phát sinh
## commands 
- `docker run` bắt đầu container
- `docker run -it` bắt đầu 1 vùng chứa tương tác 
- `docker run -d` bắt đầu 1 container tách rời 
- `docker ps` liệt kê các container đang chạy 
- `docker stop` dừng container
- `docker run --name <container-name> <image-name >` băt dầu vùng chứa bằng 1 tên 
- `docker ps -f "name=<container-name>` lọc container đang chạy theo tên 
- `docker logs <container-id>` xem nhật ký hiện có của vùng chứa 
- `docker logs -f <container-id>` xem nhật ký trực tiếp cho cùng chứa 
- `docker container rm <container-id>` loại bỏ container đã dừng 
- `docker pull <image >` kéo 1 hình ảnh 
- `docker pull <image_name>:<image_version>` kéo 1 phiên bản cụ thể của 1 hình ảnh 
- `docker images` liệt kê tất cả images
- `docker image rm` xóa hình ảnh 
- `docker container prune` loại bỏ tất cả các container đã dừng 
- `docker image prune -a` xóa tất cả hình ảnh 
- `docker volume` 
- `docker volume create <volume_name>`
- `docker volume ls` 
- `docker volume inspect` 


