---
layout: pos
title: 基础JavaScript
date: 2022-04-29 15:26:45
categories:
- JavaScript算法和数据结构
tags:
- JavaScript
toc: true
readmore: true
sticky: 0
comments: true
---

JavaScript 是一种用于网页交互的脚本语言。它和 HTML 和 CSS 一样，是网站的核心技术之一。所有现代浏览器都支持 JavaScript。

<!-- more -->
## 给代码添加注释
被注释的代码块在 JavaScript 之中是不会执行的。 在代码中写注释，是一个可以让你自己和以后的其他人理解代码作用的好方法。

JavaScript有两种写注释的方法。

使用 // 注释掉当前行的代码。 这是一个行内注释：

// This is an in-line comment.
你也可以使用多行注释来注释你的代码，使用 /* 开始， */ 结束。 这是一个多行注释：

/* This is a
multi-line comment */
> <strong>最佳实践</strong>当你写代码的时候，你应该时不时的添加注释来解释你写的代码的作用。 适当的注释能让别人和你未来的自己更容易看懂代码。
## 声明变量
在计算机科学中，数据就是一切，它对于计算机意义重大。 JavaScript 提供八种不同的数据类型，它们是 undefined（未定义）、null（空）、boolean（布尔型）、string（字符串）、symbol、number（数字）、bigint（可以表示任意大的整数）和 object（对象）。

例如，计算机区分数字，例如 12，和由字符组成的字符串 strings，例如 "12"、"dog" 或 "123 cats"。 计算机可以对数字执行数学运算，但不能对字符串执行数学运算。

变量允许计算机以一种动态的形式来存储和操作数据， 即通过操作指向数据的指针而不是数据本身来实现。 以上八种数据类型中的任何一种都可以存储到一个变量中。

变量非常类似于你在数学中使用的 x、y 变量，都是以一个简单命名的名称来代替我们赋值给它的数据。 计算机中的变量与数学中的变量不同的是，计算机可以在不同的时间存储不同类型的变量。

通过在变量前面使用关键字 var，声明一个变量，例如：
```JavaScript
var ourName;
```
上面代码的意思是创建一个名为 ourName 的变量。 在 JavaScript 中我们以分号结束语句。 
> 注意: 变量名称可以由数字、字母、美元符号 $ 或者下划线 _ 组成，但是不能包含空格或者以数字为开头。
## 使用赋值运算符存储值
在 JavaScript 中，你可以使用赋值（assignment）运算符 （=）将值存储在变量中。
```JavaScript
myVariable = 5;
```
这条语句把 Number 类型的值 5 赋给变量 myVariable。

在将值赋给运算符左侧的变量之前，将先执行 = 运算符右侧的所有运算。
```JavaScript
var myVar;
myVar = 5;
```
首先，此代码创建一个名为 myVar 的变量。 然后，数值 5 被赋给变量 myVar。 现在，如果 myVar 再次出现在代码中，程序将会将它视为 5。
## 使用赋值运算符存储值
在 JavaScript 中，你可以使用赋值（assignment）运算符 （=）将值存储在变量中。
```JavaScript
myVariable = 5;
```
这条语句把 Number 类型的值 5 赋给变量 myVariable。

在将值赋给运算符左侧的变量之前，将先执行 = 运算符右侧的所有运算。
```JavaScript
var myVar;
myVar = 5;
```
首先，此代码创建一个名为 myVar 的变量。 然后，数值 5 被赋给变量 myVar。 现在，如果 myVar 再次出现在代码中，程序将会将它视为 5。
## 使用赋值运算符初始化变量
通常在声明变量的时候会给变量初始化一个初始值。
```JavaScript
var myVar = 0;
```
创建一个名为 myVar 的变量，并指定其初始值为 0。
## 声明字符串变量
之前，你使用以下代码声明变量：
```JavaScript
var myName;
```
但是你也可以像这样声明一个字符串变量：
```JavaScript
var myName = "your name";
```
"your name" 被称为 string literal。 字符串文字或字符串是用单引号或双引号括起来的一系列零个或多个字符。
## 理解未初始化的变量
当 JavaScript 中的变量被声明的时候，程序内部会给它一个初始值 undefined。 当你对一个值为 undefined 的变量进行运算操作的时候，算出来的结果将会是 NaN，它的意思是 "Not a Number"。 如果你用 undefined 变量连接一个字符串，你将得到一个 undefined 的 字符串。
## 了解变量名区分大小写
在 JavaScript 中所有的变量和函数名都是大小写敏感的。 要区别对待大写字母和小写字母。

MYVAR 与 MyVar 和 myvar 是不同的变量。 这有可能导致出现多个相似名字的变量。 所以强烈地建议你，为了保持代码清晰不要使用这一特性。

使用驼峰命名法（camelCase）来书写一个 Javascript 变量。 在驼峰命名法（camelCase）中，变量名的第一个单词的首写字母小写，后面的单词的第一个字母大写

示例：
```JavaScript
var someVariable;
var anotherVariableName;
var thisVariableNameIsSoLong;
```
## 探索 var 和 let 关键字之间的差异
使用 var 关键字声明变量的最大问题之一是你可以轻松覆盖变量声明：
```JavaScript
var camper = "James";
var camper = "David";
console.log(camper);
```
在上面的代码中，camper 变量最初声明为 James，然后被覆盖为 David。 然后控制台显示字符串 David。

在小型应用程序中，你可能不会遇到此类问题。 但是随着你的代码库变大，你可能会意外地覆盖一个你不打算覆盖的变量。 由于此行为不会引发错误，因此搜索和修复错误变得更加困难。

ES6 中引入了一个名为 let 的关键字，这是对 JavaScript 的一次重大更新，以解决与 var 关键字有关的潜在问题。

如果将上面代码中的 var 替换为 let ，则会导致错误：
```JavaScript
let camper = "James";
let camper = "David";
```
该错误可以在你的浏览器控制台中看到。

所以不像 var，当你使用 let 时，同名的变量只能声明一次。
## 使用 const 关键字声明只读变量
关键字 let 并不是声明变量的唯一新方法。 在 ES6 中，你还可以使用 const 关键字声明变量。

const 具有 let 的所有出色功能，另外还有一个额外的好处，即使用 const 声明的变量是只读的。 它们是一个常量值，这意味着一旦一个变量被赋值为 const，它就不能被重新赋值：
```JavaScript
const FAV_PET = "Cats";
FAV_PET = "Dogs";
```
由于重新分配 FAV_PET 的值，控制台将显示错误。

你应该始终使用 const 关键字命名不想重新分配的变量。 这有助于避免给一个常量进行额外的再次赋值。

> 注意： 通常，开发者会用大写字母作为常量标识符，用小写字母或者驼峰命名作为变量（对象或数组）标识符。
## 加法运算
Number 是 JavaScript 中的一种数据类型，用来表示数值。

现在我们来尝试在 JavaScript 中做加法运算。

JavaScript 中，我们通过符号 + 来进行加法运算。

代码示例:

const myVar = 5 + 10;
现在，变量 myVar 的值为 15。
## 数字递增
使用 ++，我们可以很容易地对变量进行自增或者 +1 运算。

i++;
等效于：

i = i + 1;
> 注意：i++; 这种写法省去了书写等号的必要。
## 数字递减
使用自减符号 --，你可以很方便地对一个变量执行自减或者 -1 运算。

i--;
等效于：

i = i - 1;
> 注意：i--; 这种写法省去了书写等号的必要。
## 求余运算
remainder 求余运算符 % 返回两个数相除得到的余数

示例

5 % 2 = 1 因为
Math.floor(5 / 2) = 2 （商）
2 * 2 = 4
5 - 4 = 1 （余数）
用法
在数学中，判断一个数是奇数还是偶数，只需要判断这个数除以 2 得到的余数是 0 还是 1。

17 % 2 = 1（17 是奇数）
48 % 2 = 0（48 是偶数）
提示余数运算符（remainder）有时被错误地称为“模数”运算符。 它与模数非常相似，但不能用于负数的运算。
## 转义字符串中的引号
定义一个字符串必须要用单引号或双引号来包裹它。 那么当你的字符串里面包含引号 " 或者 ' 时该怎么办呢?

在 JavaScript 中，可以通过在引号前面使用反斜杠（\）来转义引号。
```JavaScript
const sampleStr = "Alan said, \"Peter is learning JavaScript\".";
```
有了转义符号，JavaScript 就知道这个单引号或双引号并不是字符串的结尾，而是字符串内的字符。 所以，上面的字符串打印到控制台的结果为：
```JavaScript
Alan said, "Peter is learning JavaScript".
```
## 用单引号引用字符串
JavaScript 中的字符串可以使用开始和结束都是同类型的单引号或双引号表示。 与其他一些编程语言不同的是，单引号和双引号的功能在 JavaScript 中是相同的。
```JavaScript
const doubleQuoteStr = "This is a string"; 
const singleQuoteStr = 'This is also a string';
```
当你需要在一个字符串中使用多个引号的时候，你可以使用单引号包裹双引号或者相反。 常见的场景比如在字符串中包含对话的句子需要用引号包裹。 另外比如在一个包含有 <a> 标签的字符串中，标签的属性值需要用引号包裹。
```JavaScript
const conversation = 'Finn exclaims to Jake, "Algebraic!"';
```
然而，如果你需要在其中使用外面的引号，这就成为一个问题。 记住，一个字符串在开头和结尾处有相同的引号。 要知道，字符串在开头和结尾都有相同的引号，如果在中间使用了相同的引号，字符串会提前中止并抛出错误。
```JavaScript
const goodStr = 'Jake asks Finn, "Hey, let\'s go on an adventure?"'; 
const badStr = 'Finn responds, "Let's go!"';
```
在这里 badStr 会产生一个错误。

在上面的 goodStr 中，通过使用反斜杠 \ 转义字符可以安全地使用两种引号。

> 提示： 不要混淆反斜杠 \ 和斜杠 /。 它们不是一回事。