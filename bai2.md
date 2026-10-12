# Bài 2: Khởi chạy Web Server Nginx với Port Mapping

## 1. Khởi chạy Nginx container
Chạy container `nginx:alpine` ở chế độ chạy ngầm (`-d`), đặt tên là `my-web` và ánh xạ cổng máy host `8080` vào cổng container `80`:
```bash
docker run -d -p 8080:80 --name my-web nginx:alpine
```

Kiểm tra trạng thái container đang chạy:
```bash
docker ps
```

## 2. Kiểm tra phản hồi Web Server
Gửi request kiểm tra kết nối tới container thông qua cổng 8080:
```bash
curl http://localhost:8080
```

Kết quả phản hồi (chứa nội dung HTML mặc định của Nginx):
```html
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
...
<h1>Welcome to nginx!</h1>
...
</html>
```

## 3. Dọn dẹp container
Dừng và xóa container `my-web` sau khi thử nghiệm xong:
```bash
docker stop my-web && docker rm my-web
```