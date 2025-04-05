# docker

ngix dùng để hiển thị web, revese proxy chuyển request đến server khác, cân bằng tải, hỗ trợ http
thường dùng cho nodejs php

-d: chạy ngầm
docker exec -it <container_id> /bin/sh : truy cập vào container để gõ, thoát ra bằng Ctrl D

docker run -d nginx
👉 Chạy nginx trong chế độ nền (background - detached mode).
docker stop <container_id>
docker rm <container_id>

 13. docker container prune
👉 Xóa tất cả container đã dừng để dọn dẹp.

✅ 14. docker rmi <image_id>
👉 Xóa image không dùng đến.

15. docker image prune -a
👉 Xóa tất cả image không được sử dụng (ngay cả khi đã tạo)

docker run -d -v mydata:/data nginx
👉 Gắn volume mydata vào /data trong container để lưu trữ dữ liệu.
docker run -d --name my_nginx nginx
👉 Chạy container nginx và đặt tên là my_nginx.
docker run -d -e MY_ENV=hello_world nginx
👉 Truyền biến môi trường MY_ENV=hello_world khi chạy container

FROM nginx
COPY index.html /usr/share/nginx/html/index.html
Viết Dockerfile: dùng image nginx và chép file index.html vào thư mục web.
lưu trong container tại đường dẫn /usr/share/nginx/html/index.html

👉build dockerfile
docker build -t my_nginx_image .

👉 Tạo image mới từ Dockerfile, đặt tên là my_nginx_image.
docker run -d -p 8080:80 my_nginx_image
👉 Chạy image vừa tạo và mở port 8080 cho trình duyệt truy cập.
