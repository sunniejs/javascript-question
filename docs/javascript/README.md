### JavaScript 题目 前端面试题目

题目和答案通过网络整理，如有错误欢迎 pr 修正。

题目可能不会按顺序添加，不要直接拉到最后哦，多看几遍吧，温故而知新。

答案被折叠，点击即可查看答案。:heart:

---

#### js 七种数据类型？

<details><summary><b>答案</b></summary>
<p>

`Boolean`  
`Null`  
`Undefined`  
`Number`  
`String`  
`Object`  
`Symbol` (ECMAScript 6 新定义)  
(ES6 之前)其中 5 种为基本类型:`string`,`number`,`boolean`,`null`,`undefined`  
ES6 出来的 `Symbol` 也是原始数据类型 ，表示独一无二的值  
`Object` 为引用类型(范围挺大),也包括数组、函数

</p>
</details>

---

#### js 有哪几种方法定义函数？

<details><summary><b>答案</b></summary>
<p>

函数声明表达式

```javascript
var func = function add(a, b) {
    return a + b
}
```

function 操作符

```javascript
var func = function(a, b) {
    return a + b
}
```

Function 构造函数

```javascript
var func = new Function('a', 'b', 'return a + b')
```

ES6:arrow function

```javascript
var func = (a, b) => {
    return a + b
}
```

</p>
</details>

---

#### `null` 和 `undefined` 的差异？

<details><summary><b>答案</b></summary>
<p>

相同点:

在 `if` 判断语句中,值都默认为 `false`  
大体上两者都是代表无,具体看差异

差异:

`null` 转为数字类型值为 0,而 `undefined` 转为数字类型为 `NaN`(Not a Number)  
`undefined` 是代表调用一个值而该值却没有赋值,这时候默认则为 `undefined`  
`null` 是一个很特殊的对象,最为常见的一个用法就是作为参数传入(说明该参数不是对象)  
设置为 `null` 的变量或者对象会被内存收集器回收

</p>
</details>

---

#### 开发中用到了哪些 ES6 的新特性？

<details><summary><b>答案</b></summary>
<p>

1. `let` (声明变量) `const` (声明常量,常量不能修改的量)
2. `class` (创建类)
3. `import/export` (基于 ES6 的模块规范创建导入/导出模块(文件/组件))
4. `new Set` (数组去重)
5. `Symbol`(唯一的值) `var a = Symbol('sunnie')`
6. `...ary` (展开运算符、剩余运算符)
7. `${}` 模板字符串
8. 解构赋值 `let {a} = obj; let [b] = ary`
9. `for of` 循环
10. `()=>{}` 箭头函数
11. 数组新增方法：`flat、find、findIndex`
12. 对象新增方法： `Object.assign() Object.values() Object.keys() Object.create()`


</p>
</details>

---

#### `var` , `let` 和 `const` 的区别是什么？

<details><summary><b>答案</b></summary>
<p>
记住关键词：顶部变量属性、变量提升、暂时性死区、重复声明、初始值和作用域然后从这几个方向解释。

| 声明方式 | 顶部变量属性 | 变量提升 | 暂时性死区 | 重复声明 | 初始值 | 作用域 |
| -------- | ------------ | -------- | ---------- | -------- | ------ | ------ |
| var      | 是           | 允许     | 不存在     | 允许     | 不需要 | 除块级 |
| let      | 不是         | 不允许   | 存在       | 不允许   | 不需要 | 块级   |
| const    | 不是         | 不允许   | 存在       | 不允许   | 需要   | 块级   |

**顶部变量属性**： `var` 声明的变量会挂载在 window 上，而 `let` 和 `const` 声明的变量不会  
**变量提升** ： `var` 变量可在声明之前使用，`let` 和 `const` 不可以  
 **暂时性死区**：`var`不存在暂时性死区，在代码块中，用 `let` 或 `const` 声明变量之前，使用会抛出异常 (暂时性死区)
**重复声明** ： `var`允许重复声明，`let` 和 `const` 命令声明的变量不允许重复声明  
 **初始值**： `var`和 `let`可以没有初始值，由于 `const` 声明的是只读的常量，一旦声明，就必须立即初始化，声明之后值不能改变  
 **作用域**： `var` 没有块级作用域，`let` 和 `const`有块级作用域

**拓展：修改 `const` 对象的某个属性会报错吗？**  
因为对象是引用类型的，`const`仅保证指针不发生改变，修改对象的属性不会改变对象的指针，所以是被允许的。

**拓展：输出什么？**

```javascript
console.log(a) // undefined
var a = 2

console.log(b) //报错，Uncaught ReferenceError: b is not defined
let b = 1
```

</p>
</details>

---

#### 几种 `for` 循环，以及区别？

<details><summary><b>答案</b></summary>
<p>

-   `forEach` `for`循环的简化,不能中断，没有 `break/continue` 方法，没有返回值。
-   `map` 只能遍历数组，不能中断，返回值是修改后的数组。

```javascript
const arr = [1, 2, 3, 4, 5]
for (let i = 0; i < arr.length; i++) {}
// ES5 forEach
arr.forEach(function(item) {})
// ES5 every
arr.every(function(item) {
    return true
})
// ES5 for in 循环的是 key
const object = { name: 'sunnie', age: 18 }
for (let key in object) {
    console.log(key)
}
```

```javascript
// ES6 for of 循环的是 value
for (let item of object) {
    console.log(key)
}
```

**拓展：for...in 迭代和 for...of 有什么区别**

for...in 循环出的是 key，for...of 循环出的是 value

</p>
</details>

---

#### ES5,ES6 如何查找一个元素？

<details><summary><b>答案</b></summary>
<p>

</p>
</details>

---

#### 什么是类数组(伪数组)，如何转换成数组 ？

<details><summary><b>答案</b></summary>
<p>

`类数组(Array-Like Objects)` 是一个类似数组的对象，比如 `arguments` 对象，还有 `DOM API` 返回的 `NodeList` 对象都属于类数组对象。

类数组对象有下面两个特性：

-   具有：指向对象元素的数字索引下标和 `length` 属性
-   不具有：比如 `push` 、`shift`、 `forEach` 以及 `indexOf` 等数组对象具有的方法

**类数组对象转数组方法：**

```javascript
function fn() {
    // ES5 方法1:
    var arr = Array.prototype.slice.call(arguments)

    // ES6 方法1:
    let arr = Array.from(arguments)
    // ES6 方法2:
    let arr = [...arguments]

    // 以上三种请任选一种执行测试，为方便写在一起了
    arr.push(4) // arr -> [1, 2, 3, 4]
}
fn(1, 2, 3)
```

</p>
</details>

---

#### 箭头函数和普通函数的区别？

<details><summary><b>答案:star:</b></summary>
<p>

-   箭头函数作为匿名函数，不能作为构造函数，不能使用 `new` 运算符
-   箭头函数不绑定 `auguments`，用 `rest` 参数...解决
-   箭头函数会捕获其上下文的 `this` 值，作为自己的 `this` 值
-   箭头函数当方法使用的时候，没有定义 this 绑定
-   使用`call()`和 `apply()`调用，传入参数时，参数一的改变对 `this` 没有影响
-   箭头函数没有原型属性
-   箭头函数不能当做 `Generator` 函数，不能使用 `yiel` 关键字。

</p>
</details>

---

#### JS 怎么实现一个类,怎么实例化这个类？

<details><summary><b>答案</b></summary>
<p>

Javascript 传统方法是通过构造函数定义并生成新对象。

```javascript
function Parent(name) {
    this.name = name
}
Parent.prototype.eat = function() {
    console.log('eat')
}
var child = new Child('parent')
```

ES6 引入了 `CLASS` 概念，`constructor`方法就是构造函数，定义 `类` 的方法时，前面不需要加 `function` 保留字，方法之前不需要逗号。

```javascript
class Parent {
    constructor(name) {
        this.name = name
    }
    eat() {
        console.log('eat')
    }
}
let child = new Child('parent')
```

</p>
</details>

---

#### JS 怎么继承类？

<details><summary><b>答案</b></summary>
<p>

```javascript
// ES5 call 继承
function Parent() {
    this.name = 'parent'
}
function Child() {
    Parent.call(this)
    this.type = 'child'
}
```

缺点：只实现了部分继承 ，父类原型对象 `prototype` 上的方法无法继承。

```javascript
// ES5 借助原型链
function Parent() {
    this.name = 'parent'
    this.play = [1, 2, 3]
}
function Child() {
    Parent.call(this)
}
Child.prototype = new Parent()
```

通过上面的方法继承，尝试修改实例属性

```javascript
var s1 = new Child()
var s2 = new Child()
s1.play.push(4)
console.log(s1.play, s2.play) // [1,2,3,4],[1,2,3,4]
```

缺点：实例化两个对象，修改其中一个对象的继承属性，另外也会改变。因为两个实例的原型对象一样。

```javascript
// ES5 借助Call和原型链
function Parent() {
    this.name = 'parent'
    this.play = [1, 2, 3]
}
function Child() {
    Parent.call(this)
    this.type = 'child'
}
Child.prototype = new Parent()
```

缺点：多执行了一次构造函数会 `Child3.prototype = new Parent()`

```javascript
function Parent() {
    this.name = 'parent'
    this.play = [1, 2, 3]
}
function Child() {
    Parent.call(this)
    this.type = 'child'
}
Child.prototype = Parent.prototype
```

缺点：多执行了一次构造函数会 `Child3.prototype = new Parent()`

```javascript
// 只实现了部分继承 ，prototype上的没有被继承
function Animal(type) {
    this.type = type
}
function Dog() {
    Animal.call(this)
}
```

```javascript
// ES6 实现继承
class Animal {
    construtor(type) {
        this.type = type
    }
    eat() {
        console.log('eat')
    }
}
class Dog extends Animal {
    construtor(type) {
        supper(type)
    }
}
```

</p>
</details>

---

#### ES6 `Set()` `Map()` 添加值得方法？

<details><summary><b>答案</b></summary>
<p>

添加值方法： `Set` 使用`add`添加，`Map` 使用`set`添加

```javascript
// Set
let mySet = new Set()
mySet.add(1)
// Map
const myMap = new Map()
const o = { p: 'hello' }
myMap.set(o, 'world')
```

</p>
</details>

---

#### es6 class static 解释？如何继承 static？

<details><summary><b>答案</b></summary>
<p>

类相当于实例的原型，所有在类中定义的方法，都会被实例继承。如果在一个方法前，加上`static`关键字，就表示该方法不会被实例继承，而是直接通过类来调用，这就称为“静态方法”。

-   静态方法调用直接在类上进行，而在类的实例上不可被调用。
-   父类的静态方法，可以被子类继承。

```javascript
class Foo {
    static classMethod() {
        return 'hello'
    }
}
// 静态方法调用直接在类上进行，而在类的实例上不可被调用。
Foo.classMethod() // 'hello'
var foo = new Foo()
foo.classMethod() // TypeError: foo.classMethod is not a function

// 父类的静态方法，可以被子类继承。
class Bar extends Foo {}
Bar.classMethod() // 'hello'
```

</p>
</details>

---

#### 什么闭包,闭包有什么用？

<details><summary><b>答案:star:</b></summary>
<p>

</p>
</details>

---

#### JS 如何获取函数所有参数？

知识点：`rest参数` `类数组`

<details><summary><b>答案</b></summary>
<p>

```javascript
// ES5
function sum() {
    console.log(arguments)
}
// ES6
function sum(...rest) {
    // rest 是数组
    console.log(rest)
}
sum(1, 2, 3)
```

</p>
</details>

---

#### 用箭头函数实现一个数组排序？

知识点：`sort` `箭头函数`

<details><summary><b>答案</b></summary>
<p>

```javascript
const arr = [10, 5, 40, 25, 1000, 1]

arr.sort((a, b) => {
    return a - b
})
console.log(arr) // [1, 5, 10, 25, 40, 1000]
```

</p>
</details>

---

#### 如何用箭头函数时间一个数组排序？

知识点：`Object`

<details><summary><b>答案</b></summary>
<p>

</p>
</details>

---

#### 深拷贝和浅拷贝的区别，以及实现？

<details><summary><b>答案:star:</b></summary>
<p>

`浅拷贝`只复制指向某个对象的指针，而不复制对象本身，新旧对象还是共享同一块内存。  
`深拷贝`会另外创造一个一模一样的对象，新对象跟原对象不共享内存，修改新对象不会改到原对象。

**如何实现浅拷贝:**

```javascript
function clone(target) {
    let cloneTarget = {}
    for (const key in target) {
        cloneTarget[key] = target[key]
    }
    return cloneTarget
}
```

**如何实现深拷贝:**

如果你的对象**没有**复杂类型的数据如 `Dates`, `functions`, `undefined`, `Infinity`, `RegExps`, `Maps`, `Sets`, `Blobs`等 简单的实现方法：

```javascript
JSON.parse(JSON.stringify())
```

基础款：

```javascript
function clone(target) {
    if (typeof target === 'object') {
        let cloneTarget = {}
        for (const key in target) {
            cloneTarget[key] = clone(target[key])
        }
        return cloneTarget
    } else {
        return target
    }
}
```

拷贝的时候不能只考虑数组，还有其他类型，以及考虑性能，这里直接来看大神如何一步一步实现：  
[如何写出一个惊艳面试官的深拷贝?](https://juejin.im/post/5d6aa4f96fb9a06b112ad5b1)

**ES6 `Object.assign()` 是深拷贝还是浅拷贝？**

`Object.assign`方法实行的是浅拷贝，不是深拷贝。  
也就是说，如果源对象某个属性的值是对象，那么目标对象拷贝得到的是这个对象的引用。  
注意:object 只有一层的时候，是深拷贝

```javascript
let obj = {
    username: 'sunnie',
}
let obj2 = Object.assign({}, obj)
obj2.username = 'change' // `深拷贝`修改新对象不会改到原对象
console.log(obj) // {username: "sunnie"}
```

</p>
</details>

---

#### this？

<details><summary><b>答案</b></summary>
<p>

</p>
</details>

---

#### `call`、`apply`、`bind`的区别,以及实现？

<details><summary><b>答案:star:</b></summary>
<p>

`apply` 、`call`、`bind` 都是可以改变 `this` 的指向的，但是这三个函数稍有不同。

**先说 apply 和 call 的区别**

`call()`方法接受的是参数列表，而`apply()`方法接受的是一个参数数组。

```javascript
var person = {
    value: 1,
}
function say(name, age) {
    console.log(name)
    console.log(age)
    console.log(this)
}
// call 用法
say.call(person, 'sunnie', 18)
// apply 用法
say.apply(person, ['sunnie', 18])
// kevin
// 18
// {value: 1}
```

看完之后还是很疑惑为什么会有这个玩意??

说改变`this`的指向太抽象。我们这样理解：有一个对象 `person` ,懒得给它新定义 `say` 方法，  
就通过 `call` 或 `apply`,用 `say.call(person)` 给 `person` 添加一个 `say` 方法，并执行它。  
这个时候`this` 从原来的 `window` 改成了 `person` 。

**call 实现**

思路：1.将函数设为对象的属性 2.执行该函数 3.删除该函数

```javascript
// 第一版
Function.prototype.call2 = function(context) {
    // 首先要获取调用 call 的函数，用this可以获取
    context.fn = this
    context.fn()
    delete context.fn
}
```

**apply 实现**

`apply` 与 `call` 类似，直接去看大神怎么一步一步实现

<a href="https://juejin.im/post/5907eb99570c3500582ca23c" target="_blank">JavaScript 深入之 call 和 apply 的模拟实现</a>

**bind 与 apply 、call 的区别**

`bind` 返回值为一个修改完 `this` 指向的函数，需要主动调用

```javascript
// 第一版
Function.prototype.bind2 = function(context) {
    var self = this
    return function() {
        self.apply(context)
    }
}
```

这里直接来看大神如何一步一步实现：  
<a href="https://juejin.im/post/59093b1fa0bb9f006517b906" target="_blank">JavaScript 深入之 call 和 apply 的模拟实现</a>

</p>
</details>

---

#### 如何实现防抖、节流？应用场景？

<details><summary><b>答案</b></summary>
<p>
 
**`函数防抖`(debounce):防抖就是将一段时间内连续的多次触发转化为一次触发。**

比如：我点击一个按钮，`delay`设置 3s ,我手速超快，从来不让点击间隔时间大于 3s 函数就不执行，一旦大于了 3s 就执行了

```javascript
function debounce(func, delay) {
    let timeout
    return function() {
        clearTimeout(timeout) // 如果持续触发，那么就清除定时器，定时器的回调就不会执行。
        timeout = setTimeout(() => {
            func.apply(this, arguments)
        }, delay)
    }
}
```

**`函数节流`(throttle):节流顾名思义则是将减少一段时间内触发的频率。**

比如：我点击一个按钮，`threshhold`设置 3s, 当我点第一次点击执行函数，接下来的 3s 内点都少次都没用，直到距离第一次 3s 执行第二次

```javascript
function throttle(fn, threshhold = 3000) {
    let last
    let timer
    return function() {
        const now = +new Date()
        if (last && now < last + threshhold) {
            clearTimeout(timer)
            timer = setTimeout(() => {
                last = now
                fn.apply(this, arguments)
            }, threshhold)
        } else {
            last = now
            fn.apply(this, arguments)
        }
    }
}
```

**应用场景**
mouse move 时减少计算次数：`debounce`  
input 中输入文字自动发送 ajax 请求进行自动补全： `debounce`  
ajax 请求合并，不希望短时间内大量的请求被重复发送：`debounce`  
resize window 重新计算样式或布局：`debounce` 或 `throttle`  
scroll 时触发操作，如随动效果：throttle  
对用户输入的验证，不想停止输入再进行验证，而是每 n 秒进行验证：`throttle`

</p>
</details>

---

#### ES6 Async/Await 与 Promise 区别？

<details><summary><b>答案</b></summary>
<p>

</p>
</details>

---

#### `script` 引入标签 `defer` 和 `async` 区别和相同点？

<details><summary><b>答案</b></summary>
<p>

![](https://imgs.solui.cn/questions/defer.png)

通过图片观察  
相同：

-   加 `defer` 和 `async`后，`script`读取和 `html`解析同时进行，不会阻塞 `html` 解析。  
    不同：
-   `defer`会在 `html`解析完之后执行 ， `async` 则是异步加载完 `script` 后立即执行 。
-   图中未表现出 `defer` 是按照加载顺序执行脚本的。 `async` 则是一个乱序执行，反正对它来说脚本的加载和执行是紧紧挨着的，所以不管你声明的顺序如何，只要它加载完了就会立刻执行。

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
