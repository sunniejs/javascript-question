# CSS 题目

题目和答案通过网络整理，如有错误欢迎 pr 修正。

题目可能不会按顺序添加，不要直接拉到最后哦，多看几遍吧，温故而知新。

答案被折叠，点击即可查看答案。:heart:

查看其他分类题目

:purple_heart: [JAVASCRIPT](/)  
 :heart: [HTTP](/http/README.md)

---

#### CSS 盒子模型 ？

<details><summary><b>答案</b></summary>
<p>
盒子组成: content padding  border margin

-   W3C 盒子模型 : width = content
-   IE 盒子模型 : width = content + padding + border

`box-sizing` 是 CSS3 的新的属性

box-sizing : content-box&emsp;&emsp;&emsp;&emsp;W3C 盒模型  
box-sizing : border-box&emsp;&emsp;&emsp;&emsp;IE 盒模型

 </p>
</details>

---

#### CSS position 的值 ？

<details><summary><b>答案</b></summary>
<p>

-   absolute  
    生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。
-   fixed （老 IE 不支持）
    生成绝对定位的元素，相对于浏览器窗口进行定位。
-   relative
    生成相对定位的元素，相对于其正常位置进行定位。
-   static 默认值。没有定位，元素出现在正常的流中 （忽略 top, bottom, left, right z-index 声明）。
-   inherit 规定从父元素继承 position 属性的值。

</p>
</details>

---

#### BFC 是什么 ？

<details><summary><b>答案</b></summary>
<p>

BFC(块级格式上下文)可以理解为名词，我要创建一个 BFC，是页面盒模型布局中的一种 CSS 渲染模式，相当于一个独立的容器，里面的元素和外部的元素相互不影响。

创建 BFC 的方式有：

-   html 根元素
-   float 浮动
-   绝对定位
-   overflow 不为 visiable
-   display 为表格布局或者弹性布局

BFC 主要的作用是：

-   清除浮动
-   防止同一 BFC 容器中的相邻元素间的外边距重叠问题

 </p>
</details>

---

#### CSS 选择符有哪些？哪些属性可以继承？

<details><summary><b>答案</b></summary>
<p>

-   1.id 选择器（ # myid）  
    2.类选择器（.myclassname）  
    3.标签选择器（div, h1, p）  
    4.相邻选择器（h1 + p）  
    5.子选择器（ul < li）  
    6.后代选择器（li a）  
    7.通配符选择器（ \* ）  
    8.属性选择器（a[rel = "external"]）  
    9.伪类选择器（a: hover, li: nth-child ）
-   可继承： font-size font-family color, UL LI DL DD DT;
-   不可继承 ：border padding margin width height ;

 </p>
</details>

---

#### CSS 优先级算法如何计算？ CSS3 新增伪类有那些？？

<details><summary><b>答案</b></summary>
<p>

优先级为:  
!important > 行内样式 > id > class > tag

CSS3 新增伪类举例：  
p:first-of-type 选择属于其父元素的首个 <p> 元素的每个 <p> 元素。  
p:last-of-type 选择属于其父元素的最后 <p> 元素的每个 <p> 元素。  
p:only-of-type 选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。  
p:only-child 选择属于其父元素的唯一子元素的每个 <p> 元素。  
p:nth-child(2) 选择属于其父元素的第二个子元素的每个 <p> 元素。  
:enabled、:disabled 控制表单控件的禁用状态。  
:checked，单选框或复选框被选中。

 </p>
</details>

---

#### CSS 清除浮动方法有哪些，比较好的是哪一种？

<details><summary><b>答案</b></summary>
<p>
 
 1.父元素的最后设置 `clear:both` (不推荐，增加了元素)

```html
<div class="p">
    <div class="c"></div>
    <div class="c"></div>
    <div style="clear:both"></div>
</div>
```

2.伪元素，这里我们使用 `::after`。添加一个类 `clearfix::after` (推荐，浏览器支持好)

```html
<div class="p clearfix">
    <div class="c"></div>
    <div class="c"></div>
</div>
<style>
    .clearfix::after {
        content: '.';
        display: block;
        height: 0;
        visibility: hidden;
        clear: both;
    }
    .clearfix {
        *zoom: 1; /* ie6-7 清除浮动方式 */
    }
</style>
```

3.父级 `overflow:hidden` (不推荐 ，不能和 position 配合使用，因为超出的尺寸的会被隐藏)  
4.父级 `div` 定义 `height` (不推荐 ，不灵活)  
5.父级 `div` 定义 `display:table` (不推荐 ，不灵活)

 </p>
</details>

---

#### CSS 如何实现垂直水平居中？

<details><summary><b>答案</b></summary>
<p>

1.利用 `flexbox` 布局

```html
<style>
    .flexbox {
        display: flex;
        justify-content: center; /* 水平居中 */
        align-items: center; /* 垂直居中 */
    }
</style>
```

2.利用绝对定位与 `transform`

```html
<style>
    .parent {
        position: absolute;
    }
    .parent .children {
        position: absolute;
        top: 50%;
        left: 50%;
        -webkit-transform: translate(-50%, -50%);
    }
</style>
```

3.将父元素定位，子元素绝对定位，利用 `margin` 负值为子元素宽高的一半来实现。

```html
<style>
    .parent {
        position: relative;
        background-color: #eee;
        height: 600px;
        width: 100%;
    }
    .parent .children {
        background-color: #751;
        width: 200px;
        height: 200px;
        position: absolute;
        top: 50%;
        left: 50%;
        margin: -100px 0 0 -100px;
    }
</style>
```

4.利用定位与 `margin:auto`

```html
<style>
    .parent {
        width: 100%;
        height: 600px;
        background: #09c;
        position: relative;
    }
    .children {
        width: 100px;
        height: 100px;
        background-color: #eee;
        position: absolute;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        margin: auto;
    }
</style>
```

</p>
</details>

---

#### CSS 中 `link` 和 `@import` 的区别是?？

<details><summary><b>答案</b></summary>
<p>

-   `link` 属于 html 标签，而 `@import` 是 CSS 中提供的
-   在页面加载的时候，`link` 会同时被加载，而`@import` 引用的 CSS 会在页面加载完成后才会加载引用的 CSS
-   `@import` 只有在 ie5 以上才可以被识别，而 `link` 是 html 标签，不存在浏览器兼容性问题

</p>
</details>

---

#### opacity: 0、visibility: hidden、display: none 优劣和适用场景 ？

<details><summary><b>答案</b></summary>
<p>

| 隐藏               | 元素能否点击 | 元素是否消失 | 性能               | 继承                                                       |
| ------------------ | ------------ | ------------ | ------------------ | ---------------------------------------------------------- |
| display:none       | 不能点击     | 消失         | 回流, 性能消耗较大 | 非继承属性                                                 |
| visibility: hidden | 不能点击     | 不会消失     | 重绘, 性能消耗较少 | 继承属性 ，通过设置 visibility: visible;可以让子孙节点显式 |
| opacity: 0         | 可以点击     | 不会消失     | 重绘，性能消耗较少 | 非继承属性                                                 |

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
