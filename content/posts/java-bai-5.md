+++
date = '2025-12-27T13:20:00+07:00'
draft = false
title = 'Xử lý đa luồng (Multi-threading) cho Server'
+++

## 1. Tại sao cần đa luồng?
Một Server thông thường chỉ xử lý được một Client tại một thời điểm. Để phục vụ hàng ngàn người dùng cùng lúc, chúng ta cần kỹ thuật Multi-threading (Đa luồng).

## 2. Cách hoạt động
Khi một Client mới kết nối, Server sẽ tạo ra một luồng (`Thread`) riêng để phục vụ Client đó, trong khi luồng chính tiếp tục đợi kết nối tiếp theo.

## 3. Ví dụ minh họa
```java
while (true) {
    Socket socket = serverSocket.accept();
    new Thread(new Worker(socket)).start(); // Phục vụ song song
}
