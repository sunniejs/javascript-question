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

#### `let` 和 `const` 的区别？

<details><summary><b>答案</b></summary>
<p>

-   `let` 与 `const` 都是只在声明所在的块级作用域内有效。
-   `let` 声明的变量可以改变，值和类型都可以改变，没有限制。
-   `const` 声明的变量不得改变值，这意味着，`const` 一旦声明变量，就必须立即初始化，不能留到以后赋值。

修改 `const` 对象的某个属性会报错吗？  
因为对象是引用类型的，`const`仅保证指针不发生改变，修改对象的属性不会改变对象的指针，所以是被允许的。

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

比如：我点击一个按钮，`delay`设置 3s ,我手速超快，从来不让点击间隔时间大于 3s 函数就不执行，一旦大于了 3s 就执行了

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
