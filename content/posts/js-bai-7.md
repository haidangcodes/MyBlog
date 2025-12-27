+++
date = '2025-12-27T13:30:00+07:00'
draft = false
title = 'Fetch API: Kết nối với REST Server'
+++

## 1. Fetch API là gì?
`fetch()` là phương thức hiện đại trong JavaScript giúp bạn thực hiện các yêu cầu HTTP (GET, POST...) một cách dễ dàng.

## 2. Cách sử dụng cơ bản
```javascript
fetch('[https://api.example.com/data](https://api.example.com/data)')
  .then(response => response.json())
  .then(data => console.log(data));
