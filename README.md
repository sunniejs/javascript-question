
# JavaScript 题目 前端面试题目

题目和答案通过网络整理，如有错误欢迎 pr 修正。

答案被折叠，点击即可查看答案。:heart:

* [CSS](./css/README.md)
* [HTTP](./http/README.md)
---

###### 箭头函数和普通函数的区别？

<details><summary><b>答案</b></summary>
<p>

1、箭头函数作为匿名函数，不能作为构造函数，不能使用 `new` 运算符
2、箭头函数不绑定 `auguments`，用 `rest` 参数...解决
3、箭头函数会捕获其上下文的 `this` 值，作为自己的 `this` 值
4、箭头函数当方法使用的时候，没有定义 this 绑定
5、使用`call()`和 `apply()`调用，传入参数时，参数一的改变对 `this` 没有影响
6、箭头函数没有原型属性
7、箭头函数不能当做 `Generator` 函数，不能使用 `yiel` 关键字。

</p>
</details>

---

###### js 七种数据类型

<details><summary><b>答案</b></summary>
<p>

Boolean
Null
Undefined
Number
String
Object
Symbol (ECMAScript 6 新定义)  
(ES6 之前)其中 5 种为基本类型:string,number,boolean,null,undefined
ES6 出来的 Symbol 也是原始数据类型 ，表示独一无二的值
Object 为引用类型(范围挺大),也包括数组、函数,

</p>
</details>

---

###### null 和 undefined 的差异

<details><summary><b>答案</b></summary>
<p>

相同点:

在 if 判断语句中,值都默认为 false
大体上两者都是代表无,具体看差异

差异:

null 转为数字类型值为 0,而 undefined 转为数字类型为 NaN(Not a Number)
undefined 是代表调用一个值而该值却没有赋值,这时候默认则为 undefined
null 是一个很特殊的对象,最为常见的一个用法就是作为参数传入(说明该参数不是对象)
设置为 null 的变量或者对象会被内存收集器回收

</p>
</details>
