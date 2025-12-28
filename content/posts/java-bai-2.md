+++
date = '2025-12-27T13:05:00+07:00'
draft = false
title = 'Java Networking: Tìm hiểu về lớp InetAddress và phân giải tên miền'
tags = ["Java Networking", "InetAddress", "Phân giải tên miền", "DNS Lookup Java", "Địa chỉ IP Java", "Java Network Programming", "IPv4 IPv6 Java", "getByName", "getLocalHost", "UnknownHostException", "Lập trình mạng Java"]
categories = ["Java", "Lập trình mạng", "Network Programming"]

[cover]
    image = "/MyBlog/images/post2.jpg"
    alt = "InetAddress trong Java và quá trình phân giải DNS"
    caption = "Nguồn: Blog Lập Trình Mạng"
    relative = false
+++

## 1. Giới thiệu về lớp InetAddress
Trong Java, lớp `InetAddress` là đại diện cho địa chỉ giao thức Internet (IP address). Nó cung cấp các phương thức để làm việc với cả địa chỉ IPv4 và IPv6, giúp chúng ta thực hiện các tác vụ như phân giải tên miền (DNS lookup) hoặc kiểm tra địa chỉ IP.

## 2. Phân giải tên miền (DNS Lookup)
DNS (Domain Name System) là dịch vụ giúp chuyển đổi tên miền dễ nhớ (như `www.cisco.com`) thành địa chỉ IP mà máy tính có thể hiểu được. Lớp `InetAddress` của Java hỗ trợ chức năng này rất tốt.

## 3. Ví dụ: Lấy thông tin IP của một tên miền
Đoạn mã dưới đây minh họa cách lấy địa chỉ IP của trang `www.cisco.com`:

```java
import java.net.InetAddress;
import java.net.UnknownHostException;

public class ResolveIP {
    public static void main(String[] args) {
        try {
            // Lấy địa chỉ IP của một tên miền
            InetAddress ciscoAddress = InetAddress.getByName("[www.cisco.com](https://www.cisco.com)");
            System.out.println("Tên miền: " + ciscoAddress.getHostName());
            System.out.println("Địa chỉ IP: " + ciscoAddress.getHostAddress());

            // Lấy địa chỉ IP của máy cục bộ
            InetAddress localHost = InetAddress.getLocalHost();
            System.out.println("Local Host Name: " + localHost.getHostName());
            System.out.println("Local IP Address: " + localHost.getHostAddress());

        } catch (UnknownHostException e) {
            System.err.println("Không tìm thấy tên miền hoặc lỗi mạng: " + e.getMessage());
        }
    }
}
