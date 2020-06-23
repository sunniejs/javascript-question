# HTTP 题目

题目和答案通过网络整理，如有错误欢迎 pr 修正。

题目可能不会按顺序添加，不要直接拉到最后哦，多看几遍吧，温故而知新。

答案被折叠，点击即可查看答案。:heart:

查看其他分类题目

:purple_heart: [JAVASCRIPT](/)  
 :heart: [CSS](/css/README.md)

---

#### http1 和 http2 有什么区别，http2 优势？

<details><summary><b>答案</b></summary>
<p>

相对于 HTTP1.0，HTTP1.1 的优化：
缓存处理：多了 Entity tag，If-Unmodified-Since, If-Match, If-None-Match 等缓存信息（HTTTP1.0 If-Modified-Since,Expires）
带宽优化及网络连接的使用
错误通知的管理
Host 头处理
长连接：HTTP1.1 中默认开启 Connection：keep-alive，一定程度上弥补了 HTTP1.0 每次请求都要创建连接的缺点。
相对于 HTTP1.1，HTTP2 的优化：
HTTP2 支持二进制传送（实现方便且健壮），HTTP1.x 是字符串传送
HTTP2 支持多路复用
HTTP2 采用 HPACK 压缩算法压缩头部，减小了传输的体积
HTTP2 支持服务端推送
你能说说缓存么

 </p>
</details>

---

#### CSRF（Cross-site request forgery）跨站请求伪造？

<details><summary><b>答案</b></summary>
<p>
攻击者诱导受害者进入第三方网站，在第三方网站中，向被攻击网站发送跨站请求。利用受害者在被攻击网站已经获取的注册凭证，绕过后台的用户验证，达到冒充用户对被攻击的网站执行某项操作的目的。
 </p>
</details>

---

#### 如何找到失散已久的组织？

<details><summary><b>答案</b></summary>
<p>
 
 &nbsp;&nbsp;&nbsp;&nbsp;扫描下方二维码:point_down::point_down:关注“前端女塾”

![logo](https://imgs.solui.cn/wx/640.gif ':size=262x224')  
关注公众号：回复“加群”即可加 前端仙女群

</p>
</details>

---
