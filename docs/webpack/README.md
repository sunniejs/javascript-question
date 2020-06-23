# Webpakc 题目

题目和答案通过网络整理，如有错误欢迎 pr 修正。

题目可能不会按顺序添加，不要直接拉到最后哦，多看几遍吧，温故而知新。

答案被折叠，点击即可查看答案。:heart:

查看其他分类题目

:purple_heart: [JAVASCRIPT](/)  
 :heart: [CSS](/css/README.md)
:purple_heart: [HTTP](/http/README.md)

---

#### webpack 基本配置？

<details><summary><b>答案</b></summary>
<p>
code splitting
 </p>
</details>

---

#### 如何提高 Webpack 的构建速度？

<details><summary><b>答案</b></summary>
<p>

多入口情况下，使用 CommonsChunkPlugin 来提取公共代码

-   通过 externals 配置来提取常用库
-   使用 Tree-shaking 和 Scope Hoisting 来剔除多余代码

 </p>
</details>

---

#### 如何利用 Webpack 来优化前端性能（提高性能和体验）？

<details><summary><b>答案</b></summary>
<p>

压缩代码。删除多余的代码、注释、简化代码的写法等等方式。可以利用 webpack 的 UglifyJsPlugin 和 ParallelUglifyPlugin 来压缩 JS 文件， 利用 cssnano（css-loader?minimize）来压缩 css

-   利用 CDN 加速。在构建过程中，将引用的静态资源路径修改为 CDN 上对应的路径。可以利用 webpack 对于 output 参数和各 loader 的 publicPath 参数来修改资源路径

删除死代码（Tree Shaking）。将代码中永远不会走到的片段删除掉。可以通过在启动 webpack 时追加参数--optimize-minimize 来实现

提取公共代码

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
