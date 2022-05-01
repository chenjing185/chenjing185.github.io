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
## 转义字符
引号不是字符串中唯一可以被转义（escaped）的字符。 使用转义字符有两个原因：

首先是可以让你使用无法输入的字符，例如退格。
其次是可以让你在一个字符串中表示多个引号，而不会出错。
我们在之前的挑战中学到了这个。

|代码|输出|
|:--:|:--:|
|\'|单引号|
|\"|双引号|
|\n|换行符|
|\r|回车符|
|\t|制表符|
|\b|退格|
|\f|换页符|
> 请注意，必须对反斜杠本身进行转义，它才能显示为反斜杠。
## 用加号运算符连接字符串
在 JavaScript 中，当 + 操作符被用于一个 String 类型的值的时候，它被称作拼接操作符。 你可以通过拼接其他字符串来创建一个新的字符串。

例如：
```JavaScript
'My name is Alan,' + ' I concatenate.'
```
提示： 注意空格。 拼接操作不会在两个字符串之间添加空格。所以，如果想加上空格的话，你需要自己在字符串里面添加。

例如：
```JavaScript
const ourStr = "I come first. " + "I come second.";
```
字符串 I come first. I come second. 将显示在控制台中。
## 用 += 运算符连接字符串
我们还可以使用 += 运算符来拼接字符串到现有字符串变量的结尾。 对于那些被分割成几段的长的字符串来说，这一操作是非常有用的。

提示： 注意空格。 拼接操作不会在两个字符串之间添加空格，所以，如果想要加上空格的话，你需要自己在字符串里面添加。

例如：
```JavaScript
let ourStr = "I come first. ";
ourStr += "I come second.";
```
ourStr 的值为字符串 I come first. I come second.
## 用变量构造字符串
有时候你需要创建一个类似 Mad Libs（填词游戏）风格的字符串。 通过使用连接运算符（+），你可以插入一个或多个变量来组成一个字符串。

例如：
```JavaScript
const ourName = "freeCodeCamp";
const ourStr = "Hello, our name is " + ourName + ", how are you?";
```
ourStr 值为 Hello, our name is freeCodeCamp, how are you?
## 将变量追加到字符串
就像我们可以用多行字符串字面量构建单个字符串一样，我们还可以使用加且赋值（+=）运算符将字符串追加到字符串的末尾。

示例：
```JavaScript
const anAdjective = "awesome!";
let ourStr = "freeCodeCamp is ";
ourStr += anAdjective;
```
ourStr 值为 freeCodeCamp is awesome!。
## 查找字符串的长度
你可以通过在字符串变量或字符串后面写上 .length 来获得 String 的长度。
```JavaScript
console.log("Alan Peter".length);
```
字符串 10 将会出现在控制台中。

例如，如果我们创建了一个变量 const firstName = "Ada"，我们可以通过使用 firstName.length 找出字符串 Ada 的长度属性。
## 使用方括号查找字符串中的字符
方括号表示法（Bracket notation）是一种在字符串中的特定 index（索引）处获取字符的方法。

大多数现代编程语言，如 JavaScript，不同于人类从 1 开始计数。 它们是从 0 开始计数。 这被称为基于零（Zero-based）的索引。

例如，单词 Charles 的索引 0 的字符是 C。 所以如果 const firstName = "Charles"，你可以通过 firstName[0] 得到字符串第一个字母的值。

示例：
```JavaScript
const firstName = "Charles";
const firstLetter = firstName[0];
```
firstLetter 值为字符串 C 。
## 了解字符串的不变性
在 JavaScript 中，字符串（String）的值是不可变的（immutable），这意味着一旦字符串被创建就不能被改变。

例如，下面的代码：
```JavaScript
let myStr = "Bob";
myStr[0] = "J";
```
是不会把变量 myStr 的值改变成 Job 的，因为变量 myStr 是不可变的。 注意，这并不意味着 myStr 永远不能被改变，只是字符串字面量 string literal 的各个字符不能被改变。 改变 myStr 的唯一方法是重新给它赋一个值，例如：
```JavaScript
let myStr = "Bob";
myStr = "Job";
```
## 使用 JavaScript 数组将多个值存储在一个变量中
使用数组（array），我们可以在一个地方存储多个数据。

以左方括号开始定义一个数组，以右方括号结束，里面每个元素之间用逗号隔开，例如：
```JavaScript
const sandwich = ["peanut butter", "jelly", "bread"];
```
## 将一个数组嵌套在另一个数组中
您也可以在其他数组中嵌套数组，如：
```JavaScript
const teams = [["Bulls", 23], ["White Sox", 45]];
```
这也叫做多维数组（multi-dimensional array）。
## 通过索引访问数组中的数据
我们可以使用索引（indexes）来访问数组中的数据。

数组索引与字符串一样使用方括号来表示，不同的是，它们不是指定字符，而是指定数组中的一个条目。 数组索引与字符串索引一样是从 0 开始（zero-based）的，所以数组中第一个元素的索引编号是 0。

示例
```JavaScript
const array = [50, 60, 70];
array[0];
const data = array[1];
```
现在 array[0] 的值是 50， data 的值为 60.

> **注意**:数组名与方括号之间不应该有任何空格，比如array [0] 。 尽管 JavaScript 能够正确处理这种情况，但是当其他程序员阅读你写的代码时，这可能让他们感到困惑。
## 通过索引修改数组中的数据
与字符串不同，数组的条目是 可变的 并且可以自由更改，即使数组是用 const 声明的。

示例
```JavaScript
const ourArray = [50, 40, 30];
ourArray[0] = 15;
```
ourArray 值为 [15, 40, 30]。
## 使用索引访问多维数组
我们可以把多维数组看作成是数组中的数组。 使用方括号表示法访问数组时，第一个方括号访问的是数组的最外层（第一层），第二个方括号访问的是数组的第二层，以此类推。

例如：
```JavaScript
const arr = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
  [[10, 11, 12], 13, 14]
];

arr[3];
arr[3][0];
arr[3][0][1];
```
arr[3] 为 [[10, 11, 12], 13, 14]，arr[3][0] 为 [10, 11, 12]，并且 arr[3][0][1] 为 11。

注意： 数组名与方括号之间不应该有任何空格，比如 array [0][0] 甚至是 array [0] [0] 都是不允许的。 尽管 JavaScript 能够正确处理这种情况，但是当其他程序员阅读你写的代码时，这可能让他们感到困惑。
## 使用 push() 操作数组
一个将数据添加到数组末尾的简单方法是 push() 函数。

.push() 接受一个或多个参数（parameters），并把它压入到数组的末尾。

示例：
```JavaScript
const arr1 = [1, 2, 3];
arr1.push(4);

const arr2 = ["Stimpson", "J", "cat"];
arr2.push(["happy", "joy"]);
```
arr1 现在值为 [1, 2, 3, 4]，arr2 值为 ["Stimpson", "J", "cat", ["happy", "joy"]]。
## 使用 pop() 操作数组
改变数组中数据的另一种方法是用 .pop() 函数。

.pop() 函数用来弹出一个数组末尾的值。 我们可以把这个弹出的值赋给一个变量存储起来。 换句话说就是 .pop() 函数移除数组末尾的元素并返回这个元素。

数组中任何类型的元素（数值，字符串，甚至是数组）都可以被弹出来 。
```JavaScript
const threeArr = [1, 4, 6];
const oneDown = threeArr.pop();
console.log(oneDown);
console.log(threeArr);
```
第一个 console.log 将显示值 6，第二个将显示值 [1, 4]。
## 使用 shift() 操作数组
pop() 函数用来移出数组中最后一个元素。 如果想要移出第一个元素要怎么办呢？

这时候我们就需要 .shift() 了。 它的工作原理就像 .pop()，但它移除的是第一个元素，而不是最后一个。

示例：
```JavaScript
const ourArray = ["Stimpson", "J", ["cat"]];
const removedFromOurArray = ourArray.shift();
```
removedFromOurArray 值为 Stimpson，ourArray 值为 ["J", ["cat"]]
## 使用 unshift() 操作数组
不仅可以 shift（移出）数组中的第一个元素，也可以 unshift（移入）一个元素到数组的头部。

.unshift() 函数用起来就像 .push() 函数一样，但不是在数组的末尾添加元素，unshift() 在数组的头部添加元素。

示例：
```JavaScript
const ourArray = ["Stimpson", "J", "cat"];
ourArray.shift();
ourArray.unshift("Happy");
```
在 shift、ourArray 后值为 ["J", "cat"]。 在 unshift、ourArray 后值为 ["Happy", "J", "cat"]。
## 用函数编写可重用代码
在 JavaScript 中，我们可以把代码的重复部分抽取出来，放到一个函数 （functions）中。

举个例子：
```JavaScript
function functionName() {
  console.log("Hello World");
}
```
你可以通过函数名加上后面的小括号来调用（invoke）这个函数，就像这样： functionName(); 每次调用函数时，它都会在控制台上打印消息 Hello World。 每次调用函数时，大括号之间的所有代码都将被执行。
## 将值传递给带有参数的函数
函数的参数 （parameters）在函数调用中充当传入函数的输入占位符（也叫形参）。 函数调用时，参数可以为一个或多个。 调用函数时输入（或传递 "passed"）的实际值被称为参数（arguments）。

这是带有两个参数的函数，param1 和 param2：
```JavaScript
function testFun(param1, param2) {
  console.log(param1, param2);
}
```
然后我们可以调用 testFun，就像这样： testFun("Hello", "World");。 我们传入了两个字符串参数， Hello 和 World。 在函数中，param1 等于字符串 Hello 以及 param2 等于字符串 World。 请注意，testFun 函数可以多次调用，每次调用时传递的参数会决定参数的实际值。
## 使用 return 给函数返回值
我们可以通过函数的参数（arguments）把值传入函数， 也可以使用 return 语句把数据从一个函数中传出来。

示例
```JavaScript
function plusThree(num) {
  return num + 3;
}

const answer = plusThree(5);
```
answer 的值为 8。

plusThree 带有一个参数（argument）num，并返回（return）一个等于 num + 3 的值。
## 全局作用域和函数
在 JavaScript 中，作用域涉及到变量的作用范围。 在函数外定义的变量具有**全局**作用域。 这意味着，具有全局作用域的变量可以在代码的任何地方被调用。

未使用 let 或 const 关键字声明的变量会在 global 范围内自动创建。 当在代码其他地方无意间定义了一个变量，刚好变量名与全局变量相同，这时会产生意想不到的后果。 你应该总是用 let 或 const 声明你的变量。
## 局部作用域和函数
在一个函数内声明的变量，以及该函数的参数都具有局部（local）作用域。 这意味着它们只在该函数内可见。

这是在函数 myTest 内声明局部变量 loc 的例子：
```JavaScript
function myTest() {
  const loc = "foo";
  console.log(loc);
}

myTest();
console.log(loc);
```
myTest() 函数调用将在控制台中显示字符串 foo。 console.log(loc) 行（在 myTest 函数之外）将抛出错误，因为 loc 未在函数之外定义。
## 函数中的全局作用域和局部作用域
一个程序中有可能具有相同名称的局部变量 和全局变量。 在这种情况下，局部变量将会优先于全局变量。

下面为例：
```JavaScript
const someVar = "Hat";

function myFun() {
  const someVar = "Head";
  return someVar;
}
```
函数 myFun 将会返回字符串 Head，因为局部变量的优先级更高。
## 函数也可以返回 undefined
函数一般用 return 语句来返回值，但这不是必须的。 在函数没有 return 语句的情况下，当你调用它时，该函数会执行内部代码，返回的值是 undefined。

示例
```JavaScript
let sum = 0;

function addSum(num) {
  sum = sum + num;
}
```
addSum(3);
addSum 是一个没有 return 语句的函数。 该函数将更改全局变量 sum，函数的返回值为 undefined。
## 使用返回值赋值
如果你还记得我们在使用赋值运算符存储值中的讨论的话，等号右侧的所有操作都会在赋值之前完成。 这意味着我们可以获取函数的返回值，并将其赋值给一个变量。

假设我们有一个预先定义的函数 sum ，它将两个数相加，然后：
```JavaScript
ourSum = sum(5, 12);
```
将调用 sum 函数，该函数返回 17 的值并将其分配给 ourSum 变量。
## 排队
在计算机科学中队列（queue）是一个抽象的数据结构（Data Structure），队列中的条目都是有秩序的。 新的条目会被加到队列的末尾，旧的条目会从队列的头部被移出。
例子:
```JavaScript
function nextInLine(arr, item) {
  // 只修改这一行下面的代码
  let a = 0;
  let b = 0;
  a = arr.push(item);
  b = arr.shift();
  return b;
  // 只修改这一行上面的代码
}

// 设置
const testArr = [1, 2, 3, 4, 5];

// 显示代码
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```
## 理解布尔值
另一种数据类型是布尔（Boolean）。 布尔值只能是两个值中的一个：true 或者 false。 它非常像电路开关，true 是 “开”，false 是 “关”。 这两种状态是互斥的。

> 注意： 布尔值是不带引号的。 字符串 "true" 和 "false" 不是布尔值，在 JavaScript 中也没有特殊含义。
## 严格相等
### 严格相等运算符
严格相等运算符（===）是相对相等操作符（==）的另一种比较操作符。 与相等操作符转换数据两类型不同，严格相等运算符不会做类型转换。

如果比较的值类型不同，那么在严格相等运算符比较下它们是不相等的，会返回 false 。

示例
```JavaScript
3 ===  3  // true
3 === '3' // false
```
在第二个例子中，3 是一个 Number 类型，而 '3' 是一个 String 类型。
### 严格不等运算符
严格不相等运算符（!==）与全等运算符是相反的。 这意味着严格不相等并返回 false 的地方，用严格相等运算符会返回 true，反之亦然。 严格不相等运算符不会转换值的数据类型。

示例
```JavaScript
3 !==  3  // false
3 !== '3' // true
4 !==  3  // true
```
## 比较不同值
相等运算符 (==) 和严格相等运算符 (===),如果要比较的值不是同一类型，相等运算符会先执行数据类型转换，然后比较值。 而严格相等运算符只比较值，不会进行数据类型转换。

示例

3 == '3' 返回 true ，因为 JavaScript 执行了从字符串到数字类型的转换。 3 === '3' 返回 false，因为类型不同且类型转换没有执行。

提示 在 JavaScript 中，你可以使用 typeof 运算符确定变量或值的类型，如下所示：
```JavaScript
typeof 3
typeof '3'
```
typeof 3 返回字符串 number，typeof '3' 返回字符串 string。
## 逻辑运算符
### 逻辑与运算符
有时你需要在一次判断中做多个操作。 当且仅当运算符的左边和右边都是 true，逻辑与运算符（&&）才会返回 true。

同样的效果可以通过 if 语句的嵌套来实现：
```JavaScript
if (num > 5) {
  if (num < 10) {
    return "Yes";
  }
}
return "No";
```
只有当 num 的值大于 5 并且小于10 时才会返回 Yes。 相同的逻辑可被写为：
```JavaScript
if (num > 5 && num < 10) {
  return "Yes";
}
return "No";
```
### 逻辑或运算符
只要逻辑或运算符（||）两边的任何一个运算的结果是 true，则返回 true。 否则，返回 false。

逻辑或运算符由两个竖线（||）组成。 这个按键位于退格键和回车键之间。

下面这样的语句你应该很熟悉：
```JavaScript
if (num > 10) {
  return "No";
}
if (num < 5) {
  return "No";
}
return "Yes";
```
只有当 num 大于等于 5 或小于等于 10 时，函数才返回 Yes。 相同的逻辑可以简写成：
```JavaScript
if (num > 10 || num < 5) {
  return "No";
}
return "Yes";
```
## 分支语句if与else
### 用 if 语句来表达条件逻辑
if 语句用于在代码中做出决定。 关键字 if 告诉 JavaScript 在小括号中的条件为真的情况下去执行定义在大括号里面的代码。 这种条件被称为 Boolean 条件，因为他们只可能是 true（真）或 false（假）。

当条件的计算结果为 true，程序执行大括号内的语句。 当布尔条件的计算结果为 false，大括号内的代码将不会执行。

示例
```JavaScript
function test (myCondition) {
  if (myCondition) {
    return "It was true";
  }
  return "It was false";
}

test(true);
test(false);
```
test(true) 返回字符串 It was true，test(false) 返回字符串 It was false。

当 test 被调用，并且传递进来的参数值为 true 时，if 语句会计算 myCondition 的结果，看它是否为 true。 如果条件为 true，函数会返回 It was true。 当 test 被调用，并且传递进来的参数值为 false 时，myCondition 不 为 true，并且不执行大括号后面的语句，函数返回 It was false。
### if else 语句中的逻辑顺序
if、else if 语句中的代码顺序是很重要的。

在条件判断语句中，代码的执行顺序是从上到下，所以你需要考虑清楚先执行哪一句，后执行哪一句。

这有两个例子。

第一个例子：

function foo(x) {
  if (x < 1) {
    return "Less than one";
  } else if (x < 2) {
    return "Less than two";
  } else {
    return "Greater than or equal to two";
  }
}
第二个例子更改了代码的执行顺序：

function bar(x) {
  if (x < 2) {
    return "Less than two";
  } else if (x < 1) {
    return "Less than one";
  } else {
    return "Greater than or equal to two";
  }
}
这两个函数看起来几乎一模一样，我们传一个值进去看看它们有什么区别。

foo(0)
bar(0)
foo(0) 将返回字符串 Less than one，bar(0) 将返回字符串 Less than two。
## 使用 Switch 语句从许多选项中进行选择
如果你有非常多的选项需要选择，可以使用 switch 语句。 switch 评估一个表达式，将表达式的值与 case 子句匹配。 从第一个匹配的 case 值执行语句，直到遇到 break。

这是 switch 语句的示例：
```JavaScript
switch(lowercaseLetter) {
  case "a":
    console.log("A");
    break;
  case "b":
    console.log("B");
    break;
}
```
测试 case 值使用严格相等（===）运算符进行比较。 break 告诉 JavaScript 停止执行 switch 语句。 如果遗漏了 break ，下一个语句将会被执行。