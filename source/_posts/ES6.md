---
title: ES6
date: 2022-05-05 16:25:18
categories:
- JavaScript算法和数据结构
tags:
- JavaScript
toc: true
readmore: true
sticky: 0
comments: true
---
ECMAScript（ES）是 JavaScript 的标准。因为所有主流浏览器都遵循此规范，所以 ECMAScript 和 JavaScript 是可以互换的。
<!-- more -->
## 比较 var 和 let 关键字的作用域
如果你不熟悉 let，请查看 这个挑战。

使用 var 关键字声明变量时，它是全局声明的，如果在函数内部声明则是局部声明的。

let 关键字的行为类似，但有一些额外的功能。 在代码块、语句或表达式中使用 let 关键字声明变量时，其作用域仅限于该代码块、语句或表达式。

例如：
```html
<script>
var numArray = [];
for (var i = 0; i < 3; i++) {
  numArray.push(i);
}
console.log(numArray);
console.log(i);
</script>
```
此处控制台将显示值 [0, 1, 2] 和 3。

使用 var 关键字，i 是全局声明的。 所以当 i++ 被执行时，它会更新全局变量。 此代码类似于以下内容：
```html
<script>
var numArray = [];
var i;
for (i = 0; i < 3; i++) {
  numArray.push(i);
}
console.log(numArray);
console.log(i);
</script>
```
此处控制台将显示值 [0, 1, 2] 和 3。

如果你创建一个函数，将它存储起来，稍后在使用 i 变量的 for 循环中使用。这么做可能会出现问题。 这是因为存储的函数将始终引用更新后的全局 i 变量的值。
```html
<script>
var printNumTwo;
for (var i = 0; i < 3; i++) {
  if (i === 2) {
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());
</script>
```
此处控制台将显示值 3。

可以看到，printNumTwo() 打印了 3 而不是 2。 这是因为赋值给 i 的值已经更新，printNumTwo() 返回全局的 i，而不是在 for 循环中创建函数时 i 的值。 let 关键字就不会出现这种现象：
```html
<script>
let printNumTwo;
for (let i = 0; i < 3; i++) {
  if (i === 2) {
    printNumTwo = function() {
      return i;
    };
  }
}
console.log(printNumTwo());
console.log(i);
</script>
```
在这里控制台将显示值 2 和一个错误提示 i is not defined。

i 未定义，因为它没有在全局范围内声明。 它只在 for 循环语句中被声明。 printNumTwo() 返回了正确的值，因为 let 关键字创建了三个具有唯一值（0、1 和 2）的不同 i 变量在循环语句中。
## 改变一个用 const 声明的数组
const 声明在现代 JavaScript 中有很多用例。

默认情况下，一些开发人员更喜欢使用 const 分配所有变量，除非他们知道需要重新分配值。 只有在这种情况下，他们才使用 let。

但是，重要的是要了解使用 const 分配给变量的对象（包括数组和函数）仍然是可变的。 使用 const 声明只能防止变量标识符的重新分配。
```html
<script>
const s = [5, 6, 7];
s = [1, 2, 3];
s[2] = 45;
console.log(s);
</script>
```
s = [1, 2, 3] 将导致错误。 console.log 将显示值 [5, 6, 45]。

如你所见，你可以改变对象 [5, 6, 7] 本身，变量 s 仍将指向更改后的数组 [5, 6, 45]。 像所有数组一样，s 中的数组元素是可变的，但是因为使用了 const，所以不能使用变量标识符 s 来指向一个使用赋值运算符的不同数组。
## 防止对象改变
通过之前的挑战可以看出，const 声明并不会真的保护数据不被改变。 为了确保数据不被改变，JavaScript 提供了一个函数 Object.freeze。

任何更改对象的尝试都将被拒绝，如果脚本在严格模式下运行，将抛出错误。
```html
<script>
let obj = {
  name:"FreeCodeCamp",
  review:"Awesome"
};
Object.freeze(obj);
obj.review = "bad";
obj.newProp = "Test";
console.log(obj); 
</script>
```
obj.review 和 obj.newProp 赋值将导致错误，因为我们的编辑器默认在严格模式下运行，控制台将显示值 { name: "FreeCodeCamp", review: "Awesome" }。
## 使用箭头函数编写简洁的匿名函数
在 JavaScript 里，我们会经常遇到不需要给函数命名的情况，尤其是在需要将一个函数作为参数传给另外一个函数的时候。 这时，我们会创建匿名函数。 因为这些函数不会在其他地方复用，所以我们不需要给它们命名。

这种情况下，我们通常会使用以下语法：
```html
<script>
const myFunc = function() {
  const myVar = "value";
  return myVar;
}
</script>
```
ES6 提供了其他写匿名函数的方式的语法糖。 你可以使用箭头函数：
```html
<script>
const myFunc = () => {
  const myVar = "value";
  return myVar;
}
</script>
```
当不需要函数体，只返回一个值的时候，箭头函数允许你省略 return 关键字和外面的大括号。 这样就可以将一个简单的函数简化成一个单行语句。
```html
<script>const myFunc = () => "value";</script>
```
这段代码默认会返回字符串 value。
## 编写带参数的箭头函数
和一般的函数一样，你也可以给箭头函数传递参数。
```html
<script>
const doubler = (item) => item * 2;
doubler(4);
</script>
```
doubler(4) 将返回 8。

如果箭头函数只有一个参数，则可以省略参数外面的括号。
```JavaScript
const doubler = item => item * 2;
```
可以给箭头函数传递多个参数。
```html
<script>
const multiplier = (item, multi) => item * multi;
multiplier(4, 2);
</script>
```
multiplier(4, 2) 将返回 8。
## 设置函数的默认参数
ES6 里允许给函数传入默认参数，来构建更加灵活的函数。

请看以下代码：
```html
<script>
const greeting = (name = "Anonymous") => "Hello " + name;

console.log(greeting("John"));
console.log(greeting());
</script>
```
控制台将显示字符串 Hello John 和 Hello Anonymous。

默认参数会在参数没有被指定（值为 undefined）的时候起作用。 在上面的例子中，参数 name 会在没有得到新的值的时候，默认使用值 Anonymous。 你还可以给多个参数赋予默认值。
## 将 rest 操作符与函数参数一起使用
ES6 推出了用于函数参数的 rest 操作符帮助我们创建更加灵活的函数。 rest 操作符可以用于创建有一个变量来接受多个参数的函数。 这些参数被储存在一个可以在函数内部读取的数组中。

请看以下代码：
```html
<script>
function howMany(...args) {
  return "You have passed " + args.length + " arguments.";
}
console.log(howMany(0, 1, 2));
console.log(howMany("string", null, [1, 2, 3], { }));
</script>
```
控制台将显示字符串 You have passed 3 arguments. 和 You have passed 4 arguments.。

使用 rest 参数，就不需要查看 args 数组，并且允许我们在参数数组上使用 map()、filter() 和 reduce()。
## 使用 spread 运算符展开数组项
ES6 引入了展开操作符，可以展开数组以及需要多个参数或元素的表达式。

下面的 ES5 代码使用了 apply() 来计算数组的最大值：
```html
<script>
var arr = [6, 89, 3, 45];
var maximus = Math.max.apply(null, arr);
</script>
```
maximus 的值为 89。

我们必须使用 Math.max.apply(null, arr)，因为 Math.max(arr) 返回 NaN。 Math.max() 函数中需要传入的是一系列由逗号分隔的参数，而不是一个数组。 展开操作符可以提升代码的可读性，使代码易于维护。
```html
<script>
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr);
</script>
```
maximus 的值应该是 89。

...arr 返回一个解压的数组。 也就是说，它展开数组。 然而，展开操作符只能够在函数的参数中或者数组中使用。 下面的代码将会报错：
```html
<script>const spreaded = ...arr;</script>
```
## 使用解构赋值来获取对象的值
解构赋值是 ES6 引入的新语法，用来从数组和对象中提取值，并优雅地对变量进行赋值。

有如下 ES5 代码：
```html
<script>
const user = { name: 'John Doe', age: 34 };

const name = user.name;
const age = user.age;
</script>
```
name 的值应该是字符串 John Doe， age 的值应该是数字 34。

下面是使用 ES6 解构赋值语句，实现相同效果：

<script>const { name, age } = user;</script>
同样，name 的值应该是字符串 John Doe， age 的值应该是数字 34。

在这里，自动创建 name 和 age 变量，并将 user 对象相应属性的值赋值给它们。 这个方法简洁多了。

你可以从对象中提取尽可能多或很少的值。
## 使用解构赋值从对象中分配变量
可以给解构的值赋予一个新的变量名， 通过在赋值的时候将新的变量名放在冒号后面来实现。

还是以上个例子的对象来举例：
```html
<script>const user = { name: 'John Doe', age: 34 };</script>
```
这是指定新的变量名的例子：
```html
<script>const { name: userName, age: userAge } = user;</script>
```
你可以这么理解这段代码：获取 user.name 的值，将它赋给一个新的变量 userName，等等。 userName 的值将是字符串 John Doe，userAge 的值将是数字 34。
