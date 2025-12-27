+++
date = '2025-12-27T13:15:00+07:00'
draft = false
title = 'Giao thức UDP và Datagram: Tốc độ tối đa'
+++

## 1. Đặc điểm của UDP
Khác với TCP, UDP (User Datagram Protocol) không cần thiết lập kết nối trước khi gửi dữ liệu. Điều này giúp tốc độ truyền tải cực nhanh nhưng không đảm bảo độ tin cậy tuyệt đối.

## 2. Ứng dụng thực tế
* Livestream video.
* Game online hành động nhanh.
* Các hệ thống hội thoại trực tuyến (VoIP).

## 3. Lớp DatagramPacket và DatagramSocket
Trong Java, dữ liệu UDP được đóng gói vào các `DatagramPacket` và gửi đi qua `DatagramSocket`.
