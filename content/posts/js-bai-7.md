+++
date = '2025-12-27T13:30:00+07:00'
draft = false
title = 'Fetch API: Kết nối với REST Server trong JavaScript'
tags = ["Fetch API", "JavaScript Fetch", "REST API JavaScript", "Async Await Fetch", "HTTP Request JS", "GET POST Fetch", "Promise Fetch", "Frontend Networking", "API Integration JS", "JavaScript Modern", "Web Development JS"]
categories = ["JavaScript", "Lập trình mạng", "Frontend", "REST API"]

[cover]
    image = "/MyBlog/images/post7.jpg"
    alt = "Minh họa Fetch API kết nối REST Server"
    caption = "Nguồn: Blog Lập Trình Mạng"
    relative = false
+++


## 1. Fetch API là gì?
`fetch()` là phương thức hiện đại trong JavaScript giúp bạn thực hiện các yêu cầu HTTP (GET, POST...) một cách dễ dàng.

## 2. Cách sử dụng cơ bản
```javascript
fetch('[https://api.example.com/data](https://api.example.com/data)')
  .then(response => response.json())
  .then(data => console.log(data));
