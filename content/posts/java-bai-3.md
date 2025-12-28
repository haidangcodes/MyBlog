+++
date = '2025-12-27T13:10:00+07:00'
draft = false
title = 'Lập trình TCP Socket: Cơ chế bắt tay 3 bước và truyền tin'
author = 'Trần Hải Đăng'
tags = ["TCP Socket", "TCP 3-way handshake", "Bắt tay 3 bước TCP", "Socket Programming Java", "ServerSocket Java", "Socket Java", "Lập trình mạng TCP", "Giao thức TCP", "Client-Server TCP", "Java Networking", "Transmission Control Protocol"]
categories = ["Lập trình mạng", "Java", "Network Programming", "Giao thức mạng"]

[cover]
    image = "/MyBlog/images/post3.jpg"
    alt = "Minh họa bắt tay 3 bước TCP và Socket Programming"
    caption = "Nguồn: Blog Lập Trình Mạng"
    relative = false
+++

## 1. Bản chất của giao thức TCP
TCP (Transmission Control Protocol) là giao thức hướng kết nối, đảm bảo dữ liệu truyền đi không bị lỗi, đúng thứ tự và không bị mất mát. Trước khi trao đổi dữ liệu, Client và Server phải thực hiện quy trình "Bắt tay 3 bước" (3-way handshake) để thiết lập kênh truyền.

## 2. Hình ảnh minh họa quy trình
![Sơ đồ bắt tay 3 bước TCP](https://images.viblo.asia/7f6d4d12-9c4c-4c7b-8c8c-123456789abc.png)
*Hình 1: Quy trình SYN -> SYN-ACK -> ACK trong thiết lập kết nối TCP.*

## 3. Triển khai code Java thực tế
Trong Java, chúng ta sử dụng `ServerSocket` cho phía máy chủ và `Socket` cho máy khách.

**Mã nguồn phía Server:**
```java
import java.io.*;
import java.net.*;

public class TCPServer {
    public static void main(String[] args) {
        try (ServerSocket server = new ServerSocket(9999)) {
            System.out.println("Server đang lắng nghe tại cổng 9999...");
            // Chấp nhận kết nối từ Client
            Socket socket = server.accept(); 
            
            // Luồng gửi dữ liệu cho Client
            PrintWriter writer = new PrintWriter(socket.getOutputStream(), true);
            writer.println("Kết nối thành công tới Server của Trần Hải Đăng!");
            
            socket.close();
        } catch (IOException e) { e.printStackTrace(); }
    }
}
