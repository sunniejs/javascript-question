
# HTTP 题目   

题目和答案通过网络整理，如有错误欢迎 pr 修正。

题目可能不会按顺序添加，不要直接拉到最后哦，多看几遍吧，温故而知新。

答案被折叠，点击即可查看答案。:heart:

查看其他分类题目

 :purple_heart: [JAVASCRIPT](/)  
 :heart: [CSS](/css/README.md)

---

#### http1 和http2 有什么区别，http2优势？

<details><summary><b>答案</b></summary>
<p>

相对于HTTP1.0，HTTP1.1的优化：
缓存处理：多了Entity tag，If-Unmodified-Since, If-Match, If-None-Match等缓存信息（HTTTP1.0 If-Modified-Since,Expires）
带宽优化及网络连接的使用
错误通知的管理
Host头处理
长连接：HTTP1.1中默认开启Connection：keep-alive，一定程度上弥补了HTTP1.0每次请求都要创建连接的缺点。
相对于HTTP1.1，HTTP2的优化：
HTTP2支持二进制传送（实现方便且健壮），HTTP1.x是字符串传送
HTTP2支持多路复用
HTTP2采用HPACK压缩算法压缩头部，减小了传输的体积
HTTP2支持服务端推送
你能说说缓存么

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