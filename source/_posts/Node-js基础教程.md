---
title: Node.js基础教程
date: 2025-09-15 10:30:00
updated: 2025-09-20 15:45:00
tags: [Node.js, 后端, JavaScript]
categories: [技术, 后端开发]
description: Node.js是一个基于Chrome V8引擎的JavaScript运行时，用于构建服务器端应用
keywords: Node.js, 后端, JavaScript, 服务器
author: 你的名字
permalink: node-js-tutorial/
comments: true
toc: true
cover: https://images.unsplash.com/photo-1627398242454-45a1465c2479?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80
---

# Node.js基础教程

## 什么是Node.js

Node.js是一个基于Chrome V8引擎的JavaScript运行时，它使用了一个事件驱动、非阻塞I/O的模型，使其轻量又高效。

## 核心特性

- **事件驱动**
- **非阻塞I/O**
- **单线程**
- **跨平台**

## 基本使用

```javascript
const http = require('http');

const server = http.createServer((req, res) => {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Hello World!');
});

server.listen(3000, () => {
  console.log('Server running at http://localhost:3000/');
});
```

## 总结

Node.js让JavaScript可以在服务器端运行，是现代全栈开发的重要工具。
