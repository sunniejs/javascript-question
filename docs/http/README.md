# HTTP 题目

题目和答案通过网络整理，如有错误欢迎 pr 修正。

题目可能不会按顺序添加，不要直接拉到最后哦，多看几遍吧，温故而知新。

答案被折叠，点击即可查看答案。:heart:

查看其他分类题目

:purple_heart: [JAVASCRIPT](/)  
 :heart: [CSS](/css/README.md)

---

#### http 发展历史 ？

<details><summary><b>答案</b></summary>
<p>

| 版本     | 产生时间 | 内容                                                             | 发展现状            |
| -------- | -------- | ---------------------------------------------------------------- | ------------------- |
| HTTP/0.9 | 1991 年  | 不涉及数据包传输，规定客户端和服务器之间通信格式，只能 GET 请求  | 没有作为正式的标准  |
| HTTP/1.0 | 1996 年  | 传输内容格式不限制，增加 PUT、PATCH、HEAD、 OPTIONS、DELETE 命令 | 正式作为标准        |
| HTTP/1.1 | 1997 年  | 持久连接(长连接)、节约带宽、HOST 域、管道机制、分块传输编码      | 2015 年前使用最广泛 |
| HTTP/2   | 2015 年  | 多路复用、服务器推送、头信息压缩、二进制协议等                   | 逐渐覆盖市场        |

 </p>
</details>

---

#### 简要概括一下 HTTP 的特点？

<details><summary><b>答案</b></summary>
<p>

HTTP 的特点概括如下:

`简单快速`、`灵活`、`无连接`、`无状态`

`无连接`：限制每次连接只处理一个请求。  
`无状态`：每个请求都是独立的，与前面的请求和后面的请求都是没有直接联系的。

 </p>
</details>

---

#### HTTP 报文结构是怎样的？

<details><summary><b>答案</b></summary>
<p>

HTTP 报文 有 `请求报文` 和 `响应报文` :

`请求报文` :包含 `请求行` + `请求头` + `空行` + `请求体`  
`响应报文` :包含 `响应行` + `响应头` + `空行` + `响应体`

 </p>
</details>

---

#### 在浏览器输入 URL 回车之后发生了什么？

<details><summary><b>答案</b></summary>
<p>

大致流程

1. URL 解析
2. DNS 查询
3. TCP 连接
4. 处理请求
5. 接受响应
6. 渲染页面

URL 解析: 浏览器查找当前 URL 是否存在缓存，并比较缓存是否过期

 </p>
</details>

---

#### http1 和 http2 有什么区别，http2 优势？

<details><summary><b>答案</b></summary>
<p>

相对于 HTTP1.0，HTTP1.1 的优化：

相对于 HTTP1.1，HTTP2 的优化：

`多路复用(Multiplexing)`:通过单一的 HTTP/2 连接请求发起多重的请求-响应消息，多个请求 stream 共享一个 TCP 连接，实现多留并行而不是依赖建立多个 TCP 连接。  
`首部压缩(Header Compression)`:HTTP/2 则使用了专门为首部压缩而设计的 HPACK 算法。  
`服务端推送(Server Push)`

缓存处理：多了 Entity tag，If-Unmodified-Since, If-Match, If-None-Match 等缓存信息（HTTTP1.0 If-Modified-Since,Expires）
带宽优化及网络连接的使用
错误通知的管理
Host 头处理
长连接：HTTP1.1 中默认开启 Connection：keep-alive，一定程度上弥补了 HTTP1.0 每次请求都要创建连接的缺点。

HTTP2 支持二进制传送（实现方便且健壮），HTTP1.x 是字符串传送

HTTP2 支持服务端推送
你能说说缓存么

 </p>
</details>

---

#### HTTP 和 HTTPS 的区别 ？

<details><summary><b>答案</b></summary>
<p>

HTTP 特点：
无状态：协议对客户端没有状态存储，对事物处理没有“记忆”能力，比如访问一个网站需要反复进行登录操作
无连接：HTTP/1.1 之前，由于无状态特点，每次请求需要通过 TCP 三次握手四次挥手，和服务器重新建立连接。比如某个客户机在短时间多次请求同一个资源，服务器并不能区别是否已经响应过用户的请求，所以每次需要重新响应请求，需要耗费不必要的时间和流量。
基于请求和响应：基本的特性，由客户端发起请求，服务端响应
简单快速、灵活
通信使用明文、请求和响应不会对通信方进行确认、无法保护数据的完整性

HTTPS 基于 HTTP 协议，通过 SSL 或 TLS 提供加密处理数据、验证对方身份以及数据完整性保护

HTTPS 需要到 CA 申请证书
HTTP 协议运行 TCP 之上，所有传输的内容都是明文的，HTTPS 运行在 SSL/TLS 上，SSL/TLS 运行在 tcp 上，所有传输的内容都是加密的。
HTTP 和 HTTPS 用的是完全不同的连接方式，端口也不同。前者是 80，后者是 443。
HTTPS 可以有效的防止运营商劫持，解决了防劫持的一大问题。
HTTPS 与 HTTP 最大的差距就是，HTTPS 是运行在 SSL/TLS 之上，而 SSL/TLS 运行在 tcp 上。

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
