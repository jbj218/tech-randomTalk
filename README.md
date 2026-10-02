# Tech-randomTalk · 知识杂谈

> 前后端分离开发中绕不开的「跨域」问题，从浏览器同源策略的本质讲到网关统一 CORS、Nginx 同源部署的完整方案。

这不是一篇 API 用法笔记，而是把**为什么会有跨域、浏览器到底拦的是什么、四种解决手段分别在什么架构阶段登场**一次讲透。每一条结论都配了可运行的配置代码。

## 🔍 这篇能帮你解决的问题

- 为什么浏览器地址栏直接敲 URL 不跨域，前端 JS 发请求就跨域？
- 请求明明到了服务器、Network 面板也看得到响应，为什么 JS 里报 CORS 错误？
- 网关转发到不同 IP 为什么不跨域？微服务之间 OpenFeign 调用需要处理 CORS 吗？
- `allowedOrigins("*")` 和 `allowCredentials(true)` 为什么不能同时配置？
- 预检请求（OPTIONS）为什么会被网关 / Spring Security 拦下？
- Nginx 和网关都配了 CORS 响应头会怎样？

## 📚 目录

| 文章 | 内容 |
| ---- | ---- |
| [跨域](./跨域.md) | 同源策略本质 / CORS 机制 / `@CrossOrigin` → 全局配置 → Gateway `globalcors` → 同源部署四阶段演进 / 预检请求 / JSONP 淘汰原因 / 7 个高频疑问 Q&A |

## 🛠️ 涉及技术栈

`跨域` `CORS` `同源策略` `Spring Boot` `Spring Cloud Gateway` `Nginx` `反向代理` `WebMvcConfigurer` `CorsWebFilter` `CorsFilter` `@CrossOrigin` `OPTIONS 预检` `JSONP` `前后端分离` `Vite 代理` `微服务`

## 📖 写作风格

- **从"为什么"入手**：先定位限制发生在哪一层，再谈方案，拒绝背配置
- **演进式组织**：四个阶段 = 单体注解 → 全局配置 → 网关统一 → 同源部署，跟着架构升级走
- **对比表格 + 口诀**：配置位置 / 作用范围 / 适用场景一张表收拢
- **高频疑问 Q&A**：容易混淆的 7 个点集中拆解

## ⭐ 觉得有用？

被跨域问题折磨过的话，随手点个 **Star**，让更多踩坑的人搜到这里。
