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
```html
<script>
var ourName;
</script>
```
上面代码的意思是创建一个名为 ourName 的变量。 在 JavaScript 中我们以分号结束语句。 
> 注意: 变量名称可以由数字、字母、美元符号 $ 或者下划线 _ 组成，但是不能包含空格或者以数字为开头。
## 使用赋值运算符存储值
在 JavaScript 中，你可以使用赋值（assignment）运算符 （=）将值存储在变量中。
```html
<script>
myVariable = 5;
</script>
```
这条语句把 Number 类型的值 5 赋给变量 myVariable。

在将值赋给运算符左侧的变量之前，将先执行 = 运算符右侧的所有运算。
```html
<script>
var myVar;
myVar = 5;
</script>
```
首先，此代码创建一个名为 myVar 的变量。 然后，数值 5 被赋给变量 myVar。 现在，如果 myVar 再次出现在代码中，程序将会将它视为 5。
## 使用赋值运算符存储值
在 JavaScript 中，你可以使用赋值（assignment）运算符 （=）将值存储在变量中。
```html
<script>
myVariable = 5;
</script>
```
这条语句把 Number 类型的值 5 赋给变量 myVariable。

在将值赋给运算符左侧的变量之前，将先执行 = 运算符右侧的所有运算。
```html
<script>
var myVar;
myVar = 5;
</script>
```
首先，此代码创建一个名为 myVar 的变量。 然后，数值 5 被赋给变量 myVar。 现在，如果 myVar 再次出现在代码中，程序将会将它视为 5。
## 使用赋值运算符初始化变量
通常在声明变量的时候会给变量初始化一个初始值。
```html
<script>
var myVar = 0;
</script>
```
创建一个名为 myVar 的变量，并指定其初始值为 0。
## 声明字符串变量
之前，你使用以下代码声明变量：
```html
<script>
var myName;
</script>
```
但是你也可以像这样声明一个字符串变量：
```html
<script>
var myName = "your name";
</script>
```
"your name" 被称为 string literal。 字符串文字或字符串是用单引号或双引号括起来的一系列零个或多个字符。
## 理解未初始化的变量
当 JavaScript 中的变量被声明的时候，程序内部会给它一个初始值 undefined。 当你对一个值为 undefined 的变量进行运算操作的时候，算出来的结果将会是 NaN，它的意思是 "Not a Number"。 如果你用 undefined 变量连接一个字符串，你将得到一个 undefined 的 字符串。
## 了解变量名区分大小写
在 JavaScript 中所有的变量和函数名都是大小写敏感的。 要区别对待大写字母和小写字母。

MYVAR 与 MyVar 和 myvar 是不同的变量。 这有可能导致出现多个相似名字的变量。 所以强烈地建议你，为了保持代码清晰不要使用这一特性。

使用驼峰命名法（camelCase）来书写一个 Javascript 变量。 在驼峰命名法（camelCase）中，变量名的第一个单词的首写字母小写，后面的单词的第一个字母大写

示例：
```html
<script>
var someVariable;
var anotherVariableName;
var thisVariableNameIsSoLong;
</script>
```
## 探索 var 和 let 关键字之间的差异
使用 var 关键字声明变量的最大问题之一是你可以轻松覆盖变量声明：
```html
<script>
var camper = "James";
var camper = "David";
console.log(camper);
</script>
```
在上面的代码中，camper 变量最初声明为 James，然后被覆盖为 David。 然后控制台显示字符串 David。

在小型应用程序中，你可能不会遇到此类问题。 但是随着你的代码库变大，你可能会意外地覆盖一个你不打算覆盖的变量。 由于此行为不会引发错误，因此搜索和修复错误变得更加困难。

ES6 中引入了一个名为 let 的关键字，这是对 JavaScript 的一次重大更新，以解决与 var 关键字有关的潜在问题。

如果将上面代码中的 var 替换为 let ，则会导致错误：
```html
<script>
let camper = "James";
let camper = "David";
</script>
```
该错误可以在你的浏览器控制台中看到。

所以不像 var，当你使用 let 时，同名的变量只能声明一次。
## 使用 const 关键字声明只读变量
关键字 let 并不是声明变量的唯一新方法。 在 ES6 中，你还可以使用 const 关键字声明变量。

const 具有 let 的所有出色功能，另外还有一个额外的好处，即使用 const 声明的变量是只读的。 它们是一个常量值，这意味着一旦一个变量被赋值为 const，它就不能被重新赋值：
```html
<script>
const FAV_PET = "Cats";
FAV_PET = "Dogs";
</script>
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
## 转义字符串中的引号
定义一个字符串必须要用单引号或双引号来包裹它。 那么当你的字符串里面包含引号 " 或者 ' 时该怎么办呢?

在 JavaScript 中，可以通过在引号前面使用反斜杠（\）来转义引号。
```html
<script>
const sampleStr = "Alan said, \"Peter is learning JavaScript\".";
</script>
```
有了转义符号，JavaScript 就知道这个单引号或双引号并不是字符串的结尾，而是字符串内的字符。 所以，上面的字符串打印到控制台的结果为：
```html
<script>
Alan said, "Peter is learning JavaScript".
</script>
```
## 用单引号引用字符串
JavaScript 中的字符串可以使用开始和结束都是同类型的单引号或双引号表示。 与其他一些编程语言不同的是，单引号和双引号的功能在 JavaScript 中是相同的。
```html
<script>
const doubleQuoteStr = "This is a string"; 
const singleQuoteStr = 'This is also a string';
</script>
```
当你需要在一个字符串中使用多个引号的时候，你可以使用单引号包裹双引号或者相反。 常见的场景比如在字符串中包含对话的句子需要用引号包裹。 另外比如在一个包含有 <a> 标签的字符串中，标签的属性值需要用引号包裹。
```html
<script>
const conversation = 'Finn exclaims to Jake, "Algebraic!"';
</script>
```
然而，如果你需要在其中使用外面的引号，这就成为一个问题。 记住，一个字符串在开头和结尾处有相同的引号。 要知道，字符串在开头和结尾都有相同的引号，如果在中间使用了相同的引号，字符串会提前中止并抛出错误。
```html
<script>
const goodStr = 'Jake asks Finn, "Hey, let\'s go on an adventure?"'; 
const badStr = 'Finn responds, "Let's go!"';
</script>
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
```html
'My name is Alan,' + ' I concatenate.'
```
提示： 注意空格。 拼接操作不会在两个字符串之间添加空格。所以，如果想加上空格的话，你需要自己在字符串里面添加。

例如：
```html
<script>
const ourStr = "I come first. " + "I come second.";
</script>
```
字符串 I come first. I come second. 将显示在控制台中。
## 用 += 运算符连接字符串
我们还可以使用 += 运算符来拼接字符串到现有字符串变量的结尾。 对于那些被分割成几段的长的字符串来说，这一操作是非常有用的。

提示： 注意空格。 拼接操作不会在两个字符串之间添加空格，所以，如果想要加上空格的话，你需要自己在字符串里面添加。

例如：
```html
<script>
let ourStr = "I come first. ";
ourStr += "I come second.";
</script>
```
ourStr 的值为字符串 I come first. I come second.
## 用变量构造字符串
有时候你需要创建一个类似 Mad Libs（填词游戏）风格的字符串。 通过使用连接运算符（+），你可以插入一个或多个变量来组成一个字符串。

例如：
```html
<script>
const ourName = "freeCodeCamp";
const ourStr = "Hello, our name is " + ourName + ", how are you?";
</script>
```
ourStr 值为 Hello, our name is freeCodeCamp, how are you?
## 将变量追加到字符串
就像我们可以用多行字符串字面量构建单个字符串一样，我们还可以使用加且赋值（+=）运算符将字符串追加到字符串的末尾。

示例：
```html
<script>
const anAdjective = "awesome!";
let ourStr = "freeCodeCamp is ";
ourStr += anAdjective;
</script>
```
ourStr 值为 freeCodeCamp is awesome!。
## 查找字符串的长度
你可以通过在字符串变量或字符串后面写上 .length 来获得 String 的长度。
```html
<script>
console.log("Alan Peter".length);
</script>
```
字符串 10 将会出现在控制台中。

例如，如果我们创建了一个变量 const firstName = "Ada"，我们可以通过使用 firstName.length 找出字符串 Ada 的长度属性。
## 使用方括号查找字符串中的字符
方括号表示法（Bracket notation）是一种在字符串中的特定 index（索引）处获取字符的方法。

大多数现代编程语言，如 JavaScript，不同于人类从 1 开始计数。 它们是从 0 开始计数。 这被称为基于零（Zero-based）的索引。

例如，单词 Charles 的索引 0 的字符是 C。 所以如果 const firstName = "Charles"，你可以通过 firstName[0] 得到字符串第一个字母的值。

示例：
```html
<script>
const firstName = "Charles";
const firstLetter = firstName[0];
</script>
```
firstLetter 值为字符串 C 。
## 了解字符串的不变性
在 JavaScript 中，字符串（String）的值是不可变的（immutable），这意味着一旦字符串被创建就不能被改变。

例如，下面的代码：
```html
<script>
let myStr = "Bob";
myStr[0] = "J";
</script>
```
是不会把变量 myStr 的值改变成 Job 的，因为变量 myStr 是不可变的。 注意，这并不意味着 myStr 永远不能被改变，只是字符串字面量 string literal 的各个字符不能被改变。 改变 myStr 的唯一方法是重新给它赋一个值，例如：
```html
<script>
let myStr = "Bob";
myStr = "Job";
</script>
```
## 使用 JavaScript 数组将多个值存储在一个变量中
使用数组（array），我们可以在一个地方存储多个数据。

以左方括号开始定义一个数组，以右方括号结束，里面每个元素之间用逗号隔开，例如：
```html
<script>
const sandwich = ["peanut butter", "jelly", "bread"];
</script>
```
## 将一个数组嵌套在另一个数组中
您也可以在其他数组中嵌套数组，如：
```html
<script>
const teams = [["Bulls", 23], ["White Sox", 45]];
</script>
```
这也叫做多维数组（multi-dimensional array）。
## 通过索引访问数组中的数据
我们可以使用索引（indexes）来访问数组中的数据。

数组索引与字符串一样使用方括号来表示，不同的是，它们不是指定字符，而是指定数组中的一个条目。 数组索引与字符串索引一样是从 0 开始（zero-based）的，所以数组中第一个元素的索引编号是 0。

示例
```html
<script>
const array = [50, 60, 70];
array[0];
const data = array[1];
</script>
```
现在 array[0] 的值是 50， data 的值为 60.

> **注意**:数组名与方括号之间不应该有任何空格，比如array [0] 。 尽管 JavaScript 能够正确处理这种情况，但是当其他程序员阅读你写的代码时，这可能让他们感到困惑。
## 通过索引修改数组中的数据
与字符串不同，数组的条目是 可变的 并且可以自由更改，即使数组是用 const 声明的。

示例
```html
<script>
const ourArray = [50, 40, 30];
ourArray[0] = 15;
</script>
```
ourArray 值为 [15, 40, 30]。
## 使用索引访问多维数组
我们可以把多维数组看作成是数组中的数组。 使用方括号表示法访问数组时，第一个方括号访问的是数组的最外层（第一层），第二个方括号访问的是数组的第二层，以此类推。

例如：
```html
<script>
const arr = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
  [[10, 11, 12], 13, 14]
];

arr[3];
arr[3][0];
arr[3][0][1];
</script>
```
arr[3] 为 [[10, 11, 12], 13, 14]，arr[3][0] 为 [10, 11, 12]，并且 arr[3][0][1] 为 11。

注意： 数组名与方括号之间不应该有任何空格，比如 array [0][0] 甚至是 array [0] [0] 都是不允许的。 尽管 JavaScript 能够正确处理这种情况，但是当其他程序员阅读你写的代码时，这可能让他们感到困惑。
## 使用 push() 操作数组
一个将数据添加到数组末尾的简单方法是 push() 函数。

.push() 接受一个或多个参数（parameters），并把它压入到数组的末尾。

示例：
```html
<script>
const arr1 = [1, 2, 3];
arr1.push(4);

const arr2 = ["Stimpson", "J", "cat"];
arr2.push(["happy", "joy"]);
</script>
```
arr1 现在值为 [1, 2, 3, 4]，arr2 值为 ["Stimpson", "J", "cat", ["happy", "joy"]]。
## 使用 pop() 操作数组
改变数组中数据的另一种方法是用 .pop() 函数。

.pop() 函数用来弹出一个数组末尾的值。 我们可以把这个弹出的值赋给一个变量存储起来。 换句话说就是 .pop() 函数移除数组末尾的元素并返回这个元素。

数组中任何类型的元素（数值，字符串，甚至是数组）都可以被弹出来 。
```html
<script>
const threeArr = [1, 4, 6];
const oneDown = threeArr.pop();
console.log(oneDown);
console.log(threeArr);
</script>
```
第一个 console.log 将显示值 6，第二个将显示值 [1, 4]。
## 使用 shift() 操作数组
pop() 函数用来移出数组中最后一个元素。 如果想要移出第一个元素要怎么办呢？

这时候我们就需要 .shift() 了。 它的工作原理就像 .pop()，但它移除的是第一个元素，而不是最后一个。

示例：
```html
<script>
const ourArray = ["Stimpson", "J", ["cat"]];
const removedFromOurArray = ourArray.shift();
</script>
```
removedFromOurArray 值为 Stimpson，ourArray 值为 ["J", ["cat"]]
## 使用 unshift() 操作数组
不仅可以 shift（移出）数组中的第一个元素，也可以 unshift（移入）一个元素到数组的头部。

.unshift() 函数用起来就像 .push() 函数一样，但不是在数组的末尾添加元素，unshift() 在数组的头部添加元素。

示例：
```html
<script>
const ourArray = ["Stimpson", "J", "cat"];
ourArray.shift();
ourArray.unshift("Happy");
</script>
```
在 shift、ourArray 后值为 ["J", "cat"]。 在 unshift、ourArray 后值为 ["Happy", "J", "cat"]。
## 用函数编写可重用代码
在 JavaScript 中，我们可以把代码的重复部分抽取出来，放到一个函数 （functions）中。

举个例子：
```html
<script>
function functionName() {
  console.log("Hello World");
}
</script>
```
你可以通过函数名加上后面的小括号来调用（invoke）这个函数，就像这样： functionName(); 每次调用函数时，它都会在控制台上打印消息 Hello World。 每次调用函数时，大括号之间的所有代码都将被执行。
## 将值传递给带有参数的函数
函数的参数 （parameters）在函数调用中充当传入函数的输入占位符（也叫形参）。 函数调用时，参数可以为一个或多个。 调用函数时输入（或传递 "passed"）的实际值被称为参数（arguments）。

这是带有两个参数的函数，param1 和 param2：
```html
<script>
function testFun(param1, param2) {
  console.log(param1, param2);
}
</script>
```
然后我们可以调用 testFun，就像这样： testFun("Hello", "World");。 我们传入了两个字符串参数， Hello 和 World。 在函数中，param1 等于字符串 Hello 以及 param2 等于字符串 World。 请注意，testFun 函数可以多次调用，每次调用时传递的参数会决定参数的实际值。
## 使用 return 给函数返回值
我们可以通过函数的参数（arguments）把值传入函数， 也可以使用 return 语句把数据从一个函数中传出来。

示例
```html
<script>
function plusThree(num) {
  return num + 3;
}

const answer = plusThree(5);
</script>
```
answer 的值为 8。

plusThree 带有一个参数（argument）num，并返回（return）一个等于 num + 3 的值。
## 全局作用域和函数
在 JavaScript 中，作用域涉及到变量的作用范围。 在函数外定义的变量具有**全局**作用域。 这意味着，具有全局作用域的变量可以在代码的任何地方被调用。

未使用 let 或 const 关键字声明的变量会在 global 范围内自动创建。 当在代码其他地方无意间定义了一个变量，刚好变量名与全局变量相同，这时会产生意想不到的后果。 你应该总是用 let 或 const 声明你的变量。
## 局部作用域和函数
在一个函数内声明的变量，以及该函数的参数都具有局部（local）作用域。 这意味着它们只在该函数内可见。

这是在函数 myTest 内声明局部变量 loc 的例子：
```html
<script>
function myTest() {
  const loc = "foo";
  console.log(loc);
}

myTest();
console.log(loc);
</script>
```
myTest() 函数调用将在控制台中显示字符串 foo。 console.log(loc) 行（在 myTest 函数之外）将抛出错误，因为 loc 未在函数之外定义。
## 函数中的全局作用域和局部作用域
一个程序中有可能具有相同名称的局部变量 和全局变量。 在这种情况下，局部变量将会优先于全局变量。

下面为例：
```html
<script>
const someVar = "Hat";

function myFun() {
  const someVar = "Head";
  return someVar;
}
</script>
```
函数 myFun 将会返回字符串 Head，因为局部变量的优先级更高。
## 函数也可以返回 undefined
函数一般用 return 语句来返回值，但这不是必须的。 在函数没有 return 语句的情况下，当你调用它时，该函数会执行内部代码，返回的值是 undefined。

示例
```html
<script>
let sum = 0;

function addSum(num) {
  sum = sum + num;
}
</script>
```
addSum(3);
addSum 是一个没有 return 语句的函数。 该函数将更改全局变量 sum，函数的返回值为 undefined。
## 使用返回值赋值
如果你还记得我们在使用赋值运算符存储值中的讨论的话，等号右侧的所有操作都会在赋值之前完成。 这意味着我们可以获取函数的返回值，并将其赋值给一个变量。

假设我们有一个预先定义的函数 sum ，它将两个数相加，然后：
```html
<script>
ourSum = sum(5, 12);
</script>
```
将调用 sum 函数，该函数返回 17 的值并将其分配给 ourSum 变量。
## 排队
在计算机科学中队列（queue）是一个抽象的数据结构（Data Structure），队列中的条目都是有秩序的。 新的条目会被加到队列的末尾，旧的条目会从队列的头部被移出。
例子:
```html
<script>
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
</script>
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
```html
<script>
if (num > 5) {
  if (num < 10) {
    return "Yes";
  }
}
return "No";
</script>
```
只有当 num 的值大于 5 并且小于10 时才会返回 Yes。 相同的逻辑可被写为：
```html
<script>
if (num > 5 && num < 10) {
  return "Yes";
}
return "No";
</script>
```
### 逻辑或运算符
只要逻辑或运算符（||）两边的任何一个运算的结果是 true，则返回 true。 否则，返回 false。

逻辑或运算符由两个竖线（||）组成。 这个按键位于退格键和回车键之间。

下面这样的语句你应该很熟悉：
```html
<script>
if (num > 10) {
  return "No";
}
if (num < 5) {
  return "No";
}
return "Yes";
</script>
```
只有当 num 大于等于 5 或小于等于 10 时，函数才返回 Yes。 相同的逻辑可以简写成：
```html
<script>
if (num > 10 || num < 5) {
  return "No";
}
return "Yes";
</script>
```
## 分支语句if与else
### 用 if 语句来表达条件逻辑
if 语句用于在代码中做出决定。 关键字 if 告诉 JavaScript 在小括号中的条件为真的情况下去执行定义在大括号里面的代码。 这种条件被称为 Boolean 条件，因为他们只可能是 true（真）或 false（假）。

当条件的计算结果为 true，程序执行大括号内的语句。 当布尔条件的计算结果为 false，大括号内的代码将不会执行。

示例
```html
<script>
function test (myCondition) {
  if (myCondition) {
    return "It was true";
  }
  return "It was false";
}

test(true);
test(false);
</script>
```
test(true) 返回字符串 It was true，test(false) 返回字符串 It was false。

当 test 被调用，并且传递进来的参数值为 true 时，if 语句会计算 myCondition 的结果，看它是否为 true。 如果条件为 true，函数会返回 It was true。 当 test 被调用，并且传递进来的参数值为 false 时，myCondition 不 为 true，并且不执行大括号后面的语句，函数返回 It was false。
### if else 语句中的逻辑顺序
if、else if 语句中的代码顺序是很重要的。

在条件判断语句中，代码的执行顺序是从上到下，所以你需要考虑清楚先执行哪一句，后执行哪一句。

这有两个例子。

第一个例子：
```html
<script>
function foo(x) {
  if (x < 1) {
    return "Less than one";
  } else if (x < 2) {
    return "Less than two";
  } else {
    return "Greater than or equal to two";
  }
}
</script>
```
第二个例子更改了代码的执行顺序：
```html
<script>
function bar(x) {
  if (x < 2) {
    return "Less than two";
  } else if (x < 1) {
    return "Less than one";
  } else {
    return "Greater than or equal to two";
  }
}
</script>
```
这两个函数看起来几乎一模一样，我们传一个值进去看看它们有什么区别。

foo(0)
bar(0)
foo(0) 将返回字符串 Less than one，bar(0) 将返回字符串 Less than two。
## 分支语句switch
### 使用 Switch 语句从许多选项中进行选择
如果你有非常多的选项需要选择，可以使用 switch 语句。 switch 评估一个表达式，将表达式的值与 case 子句匹配。 从第一个匹配的 case 值执行语句，直到遇到 break。

这是 switch 语句的示例：
```html
<script>
switch(lowercaseLetter) {
  case "a":
    console.log("A");
    break;
  case "b":
    console.log("B");
    break;
}
</script>
```
测试 case 值使用严格相等（===）运算符进行比较。 break 告诉 JavaScript 停止执行 switch 语句。 如果遗漏了 break ，下一个语句将会被执行。
### 在 switch 语句中添加默认选项
在 switch 语句中，你可能无法用 case 枚举出所有可能的值。 相反，你可以添加 default 语句，它会在找不到相匹配的 case 语句之后执行。 你可以把它看作是 if/else 链中最后的那个 else 语句。

default 语句应该被放到最后。
```html
<script>
switch (num) {
  case value1:
    statement1;
    break;
  case value2:
    statement2;
    break;
...
  default:
    defaultStatement;
    break;
}
</script>
```
### 在 Switch 语句添加多个相同选项
如果你忘了给 switch 的每一条 case 添加 break，那么后续的 case 会一直执行，直到遇见 break 为止。 如果你想为 switch 中的多个不同的输入设置相同的结果，可以这样写：
```html
<script>
let result = "";
switch(val) {
  case 1:
  case 2:
  case 3:
    result = "1, 2, or 3";
    break;
  case 4:
    result = "4 alone";
}
</script>
```
这样，1、2、3 都会有相同的结果。
### 用一个 Switch 语句来替代多个 if else 语句
如果你有多个选项需要选择，switch 语句写起来会比多个串联的 if/else if 语句容易些。 譬如:
```html
<script>
if (val === 1) {
  answer = "a";
} else if (val === 2) {
  answer = "b";
} else {
  answer = "c";
}
</script>
```
可以被下面替代：
```html
<script>
switch(val) {
  case 1:
    answer = "a";
    break;
  case 2:
    answer = "b";
    break;
  default:
    answer = "c";
}
</script>
```
## 从函数返回布尔值
你应该还记得相等运算符这道挑战题。 在那里我们提到，所有比较操作符都会返回 boolean：要么是 true 要么是 false。

有时人们通过 if/else 语句来做比较，像这样。
```html
<script>
function isEqual(a, b) {
  if (a === b) {
    return true;
  } else {
    return false;
  }
}
</script>
```
但有更好的方式来达到相同的效果。 既然 === 返回 true 或 false 我们可以直接返回比较结果：
```html
<script>
function isEqual(a, b) {
  return a === b;
}
</script>
```
## 函数执行到 return 语句就结束
当代码执行到 return 语句时，函数返回一个结果就结束运行了，return 后面的语句不会执行。

示例
```html
<script>
function myFun() {
  console.log("Hello");
  return "World";
  console.log("byebye")
}
myFun();
</script>
```
以上将在控制台中显示字符串 Hello 并返回字符串 World。 字符串 byebye 将永远不会在控制台中显示，因为函数在 return 语句处就退出了。
## 创建 JavaScript 对象
你之前可能听过 object 这个词。

对象和 arrays 类似，区别在于数组使用索引来访问和修改数据，而对象中的数据是通过 properties 访问的。

对象非常适合用来存储结构化数据，可以表示真实世界中的物体，比如一只猫。

这里是一个猫对象的样本：
```html
<script>
const cat = {
  "name": "Whiskers",
  "legs": 4,
  "tails": 1,
  "enemies": ["Water", "Dogs"]
};
</script>
```
在此示例中，所有属性都存储为字符串，例如 name、legs 和 tails。 然而，你也可以使用数字作为属性。 你甚至可以省略单字字符串属性中的引号，如下所示：
```html
<script>
const anotherObject = {
  make: "Ford",
  5: "five",
  "model": "focus"
};
</script>
```
然而，如果你的对象有非字符串属性的话，JavaScript 会自动将它们转为字符串。
## 通过点号表示法访问对象属性
和访问数组类似，访问对象属性有两种方式：点号表示法（.）和方括号表示法（[]）。

如果我们已经提前知道要访问的属性名，使用点号表示法是最方便的。

这里是一个用点符号（.）读取对象属性的示例：
```html
<script>
const myObj = {
  prop1: "val1",
  prop2: "val2"
};

const prop1val = myObj.prop1;
const prop2val = myObj.prop2;
</script>
```
prop1val 的值将为字符串 val1，并且prop2val 的值将为字符串 val2。
## 使用方括号表示法访问对象属性
访问对象属性的第二种方式是方括号表示法（[]）。 如果你想访问的属性名中包含空格，就必须使用方括号表示法来获取它的属性值。

当然，如果属性名不包含空格，也可以使用方括号表示法。

这是一个使用方括号表示法读取对象属性的例子：
```html
<script>
const myObj = {
  "Space Name": "Kirk",
  "More Space": "Spock",
  "NoSpace": "USS Enterprise"
};

myObj["Space Name"];
myObj['More Space'];
myObj["NoSpace"];
</script>
```
myObj["Space Name"] 将会是字符串 Kirk，myObj['More Space'] 将会是字符串 Spock，并且myObj["NoSpace"] 将会是字符串 USS Enterprise。

> **注意**，如果属性名中包含空格，就必须使用引号（单引号或双引号）将它们包裹起来。
## 通过变量访问对象属性
对对象上使用方括号表示法，还可以访问对象上作为变量值存储的属性。 当你需要遍历对象的所有属性，或者根据一个变量的值查找对应的属性值时，这种写法尤其适用。

以下是一个使用变量来访问属性的例子：
```html
<script>
const dogs = {
  Fido: "Mutt",
  Hunter: "Doberman",
  Snoopie: "Beagle"
};

const myDog = "Hunter";
const myBreed = dogs[myDog];
console.log(myBreed);
</script>
```
字符串 Doberman 将会出现在控制台中。

使用这一概念的另一种情况是：属性的名字是在程序运行期间动态收集得到的。如下所示：
```html
<script>
const someObj = {
  propName: "John"
};

function propPrefix(str) {
  const s = "prop";
  return s + str;
}

const someProp = propPrefix("Name");
console.log(someObj[someProp]);
</script>
```
someProp 的值将为字符串 propName，并且字符串 John 将会出现在控制台中。

注意，当使用变量名访问属性时，我们没有使用引号包裹它，因为我们正在使用的是变量的值，而不是变量的名字。
## 更新对象属性
在你创建了 JavaScript 对象后，你可以随时更新它的属性，就像更新任何其他变量那样。 你可以使用点或中括号操作符来更新。

举个例子，让我们看看 ourDog：
```html
<script>
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
</script>
```
既然他是一个特别愉快的狗，让我们将他的名字更改为字符串 Happy Camper。 这有两种方式来更新对象的 name 属性： ourDog.name = "Happy Camper"; 或 ourDog["name"] = "Happy Camper";。更新后，ourDog.name 的值就不再是 Camper，而是 Happy Camper。
## 给 JavaScript 对象添加新属性
你也可以像更改属性一样给 JavaScript 对象添加属性。

这里展示了如何给 ourDog 添加一个属性 bark：
```html
<script>ourDog.bark = "bow-wow";</script>
```
或者
```html
<script>ourDog["bark"] = "bow-wow";</script>
```
现在，当我们执行 ourDog.bark 时，就能得到他的叫声，bow-wow。

例如：
```html
<script>
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
};
</script>
```
ourDog.bark = "bow-wow";
## 删除对象的属性
我们同样可以删除对象的属性，例如：

delete ourDog.bark;
例如：
```html
<script>
const ourDog = {
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"],
  "bark": "bow-wow"
};
</script>
```
delete ourDog.bark;
在上面代码的最后一行中，ourDog 是这样的：
```html
<script>
{
  "name": "Camper",
  "legs": 4,
  "tails": 1,
  "friends": ["everything!"]
}
</script>
```
## 使用对象进行查找
对象和字典一样，可以用来存储键/值对。 如果数据是扁平的，你可以用对象来查找你想要的值，而不是链式使用 switch 或 if/else 语句。 当你知道你的输入数据在某个范围时，这种查找方式极为有效。

这是简单的反向字母表：
```html
<script>
const alpha = {
  1:"Z",
  2:"Y",
  3:"X",
  4:"W",
  ...
  24:"C",
  25:"B",
  26:"A"
};

alpha[2];
alpha[24];

const value = 2;
alpha[value];
</script>
```
alpha[2] 是字符串 Y，alpha[24] 是字符串 C，alpha[value] 是字符串 Y。
## 测试对象的属性
有时检查一个对象属性是否存在是非常有用的。 我们可以用对象的 .hasOwnProperty(propname) 方法来检查对象是否有指定的属性。 .hasOwnProperty() 找到该属性时返回 true，找不到该属性时返回 false。

示例
```html
<script>
const myObj = {
  top: "hat",
  bottom: "pants"
};

myObj.hasOwnProperty("top");
myObj.hasOwnProperty("middle");
</script>
```
第一个 hasOwnProperty 返回 true，第二个返回 false。
## 操作复杂对象
有时你可能希望将数据存储在一个灵活的数据结构（Data Structure）中。 JavaScript 对象是一种灵活的数据结构。 它可以储存字符串（strings）、数字（numbers）、布尔值（booleans）、数组（arrays）、函数（functions）和对象（objects）以及这些值的任意组合。

这是一个复杂数据结构的示例：
```html
<script>
const ourMusic = [
  {
    "artist": "Daft Punk",
    "title": "Homework",
    "release_year": 1997,
    "formats": [ 
      "CD", 
      "Cassette", 
      "LP"
    ],
    "gold": true
  }
];
</script>
```
这是一个包含一个对象的数组。 该对象有关于专辑的各种元数据（metadata）。 它也有一个嵌套的 formats 数组。 可以将专辑添加到顶级数组来增加更多的专辑记录。 对象将数据以一种键 - 值对的形式保存。 在上面的示例中，"artist": "Daft Punk" 有一个键为 artist 值为 Daft Punk 的属性。 JavaScript Object Notation 简称 JSON 是可以用于存储数据的数据交换格式。
```html
<script>
{
  "artist": "Daft Punk",
  "title": "Homework",
  "release_year": 1997,
  "formats": [ 
    "CD",
    "Cassette",
    "LP"
  ],
  "gold": true
}
</script>
```
> **提示**：数组中有多个 JSON 对象的时候，对象与对象之间要用逗号隔开。
## 访问嵌套对象
我们可以通过连续使用点号表示法和方括号表示法来访问对象的嵌套属性。

这是一个嵌套对象：
```html
<script>
const ourStorage = {
  "desk": {
    "drawer": "stapler"
  },
  "cabinet": {
    "top drawer": { 
      "folder1": "a file",
      "folder2": "secrets"
    },
    "bottom drawer": "soda"
  }
};

ourStorage.cabinet["top drawer"].folder2;
ourStorage.desk.drawer;
</script>
```
ourStorage.cabinet["top drawer"].folder2 将会是字符串 secrets，并且 ourStorage.desk.drawer 将会是字符串 stapler。
## 访问嵌套数组
在之前的挑战中，我们学习了在对象中嵌套对象和数组。 与访问嵌套对象类似，数组的方括号可以用来对嵌套数组进行链式访问。

下面是访问嵌套数组的例子：
```html
<script>
const ourPets = [
  {
    animalType: "cat",
    names: [
      "Meowzer",
      "Fluffy",
      "Kit-Cat"
    ]
  },
  {
    animalType: "dog",
    names: [
      "Spot",
      "Bowser",
      "Frankie"
    ]
  }
];

ourPets[0].names[1];
ourPets[1].names[0];
</script>
```
ourPets[0].names[1] 应该是字符串 Fluffy， 并且 ourPets[1].names[0] 应该是字符串 Spot。
## while 循环
你可以使用循环多次执行相同的代码。

我们将学习的第一种类型的循环称为 while 循环，当 while 指定的条件为真，循环才会执行，反之不执行。
```html
<script>
const ourArray = [];
let i = 0;

while (i < 5) {
  ourArray.push(i);
  i++;
}
</script>
```
在上面的代码里，while 循环执行 5 次把 0 到 4 的数字添加到 ourArray 数组里。
## for 循环
你可以使用循环多次执行相同的代码。

JavaScript 中最常见的循环就是 for，它可以循环指定次数。

for 循环中的可选三个表达式用分号隔开：

for (a; b; c)，其中a为初始化语句，b为条件语句，c 是最终的表达式。

初始化语句只会在执行循环开始之前执行一次。 它通常用于定义和设置你的循环变量。

循环条件语句会在每一轮循环的开始前执行，只要条件判断为 true 就会继续执行循环。 当条件为 false 的时候，循环将停止执行。 这意味着，如果条件在一开始就为 false，这个循环将不会执行。

终止循环表达式在每次循环迭代结束， 在下一个条件检查之前时执行，通常用来递增或递减循环计数。

在下面的例子中，先初始化 i = 0，条件 i < 5 为 true 时，进入循环。 每次循环后 i 的值增加 1，然后执行终止循环条件表达式 i++。
```html
<script>
const ourArray = [];

for (let i = 0; i < 5; i++) {
  ourArray.push(i);
}
</script>
```
ourArray 现在的值为 [0, 1, 2, 3, 4]。
## 使用 For 循环遍历数组
JavaScript 中的一个常见任务是遍历数组的内容。 一种方法是使用 for 循环。 下面的代码将输出数组 arr 的每个元素到控制台：
```html
<script>
const arr = [10, 9, 8, 7, 6];

for (let i = 0; i < arr.length; i++) {
   console.log(arr[i]);
}
</script>
```
记住数组的索引从零开始的，这意味着数组的最后一个元素的下标是：length - 1（数组的长度 -1）。 我们这个循环的条件是 i < arr.length，当 i 的值为 length 的时候循环就停止了。 在这个例子中，最后一个循环是 i === 4，也就是说，当 i 的值等于 arr.length - 1 时，结果输出 6。 然后 i 增加到 5，循环会终止，因为 i < arr.length 是 false。
## 循环嵌套
如果你有一个二维数组，可以使用相同的逻辑，先遍历外面的数组，再遍历里面的子数组。 下面是一个例子：
```html
<script>
const arr = [
  [1, 2], [3, 4], [5, 6]
];

for (let i = 0; i < arr.length; i++) {
  for (let j = 0; j < arr[i].length; j++) {
    console.log(arr[i][j]);
  }
}
</script>
```
这里一次输出了 arr 中的每个子元素。 提示，对于内部循环，我们可以通过 arr[i] 的 .length 来获得子数组的长度，因为 arr[i] 本身就是一个数组。
## do...while 循环
下一种循环叫作 do...while 循环。 它被称为 do...while 循环，是因为不论什么情况，它都会首先 do（运行）循环里的第一部分代码，然后 while（当）规定的条件被评估为 true（真）的时候，它会继续运行循环。
```html
<script>
const ourArray = [];
let i = 0;

do {
  ourArray.push(i);
  i++;
} while (i < 5);
</script>
```
上面的示例行为类似于其他类型的循环，由此产生的数组将看起来像 [0, 1, 2, 3, 4]。 然而，do...while 不同于其他循环的地方，是第一次循环检查失败时的行为。 让我们看看代码中的区别：这里是一个常规的 while 循环，只要 i < 5，就会在循环中运行代码：
```html
<script>
const ourArray = []; 
let i = 5;

while (i < 5) {
  ourArray.push(i);
  i++;
}
</script>
```
这个例子中，定义了一个空数组 ourArray 以及一个值为 5 的 i 。 当执行 while 循环时，因为 i 不小于 5，所以循环条件为 false，循环内的代码将不会执行。 ourArray 最终没有添加任何内容，因此示例中的所有代码执行完时，ourArray 仍然是[]。 现在，看一下 do...while 循环。
```html
<script>
const ourArray = []; 
let i = 5;

do {
  ourArray.push(i);
  i++;
} while (i < 5);
</script>
```
在这里，和使用 while 循环一样，将 i 的值初始化为 5。 执行下一行时，没有执行循环检查，直接执行花括号内的代码。 数组会添加一个元素，并在进行条件检查之前递增 i。 然后，在条件检查时因为 i 等于 6 不符合条件 i < 5，所以退出循环。 最终 ourArray 的值是 [5]。 本质上，do...while 循环确保循环内的代码至少运行一次。 让我们通过 do...while 循环将值添加到数组中。
## 使用递归代替循环
递归是函数调用自身的操作。 为了便于理解，有如下任务：计算数组内元素前 n 的元素乘积。 使用 for 循环， 可以这样做：
```html
<script>
  function multiply(arr, n) {
    let product = 1;
    for (let i = 0; i < n; i++) {
      product *= arr[i];
    }
    return product;
  }
</script>
```
下面是递归写法，注意代码里的 multiply(arr, n) == multiply(arr, n - 1) * arr[n - 1]。 这意味着可以重写 multiply 以调用自身而无需依赖循环。
```html
<script>
  function multiply(arr, n) {
    if (n <= 0) {
      return 1;
    } else {
      return multiply(arr, n - 1) * arr[n - 1];
    }
  }
</script>
```
递归版本的 multiply 详述如下。 在 base case 里，也就是 n <= 0 时，返回 1。 在 n 比 0 大的情况里，函数会调用自身，参数 n 的值为 n - 1。 函数以相同的方式持续调用 multiply，直到 n <= 0 为止。 所以，所有函数都可以返回，原始的 multiply 返回结果。

> **注意**： 递归函数在没有函数调用时（在这个例子是，是当 n <= 0 时）必需有一个跳出结构，否则永远不会执行完毕。
## 使用 JavaScript 生成随机整数
生成随机小数很棒，但随机数更有用的地方在于生成随机整数。

用 Math.random() 生成一个随机小数。
把这个随机小数乘以 20。
用 Math.floor() 向下取整，获得它最近的整数。
记住 Math.random() 永远不会返回 1。同时因为我们是在向下取整，所以最终我们获得的结果不可能有 20。 这确保了我们获得了一个在 0 到 19 之间的整数。

把操作连缀起来，代码类似于下面：
```html
<script>
Math.floor(Math.random() * 20);
</script>
```
我们先调用 Math.random()，把它的结果乘以 20，然后把上一步的结果传给 Math.floor()，最终通过向下取整获得最近的整数。
## 生成某个范围内的随机整数
我们之前生成的随机数是在 0 到某个数之间，现在我们要生成的随机数是在两个指定的数之间。

我们需要定义一个最小值 min 和一个最大值 max。

下面是我们将要使用的方法， 仔细看看并尝试理解这行代码到底在干嘛：
```html
<script>
Math.floor(Math.random() * (max - min + 1)) + min
</script>
```
## 使用 parseInt 函数
parseInt() 函数解析一个字符串返回一个整数。 下面是一个示例：
```html
<script>
const a = parseInt("007");
</script>
```
上述函数将字符串 007 转换为整数 7。 如果字符串中的第一个字符不能转换为数字，则返回 NaN。
## 使用 parseInt 函数并传入一个基数
parseInt() 函数解析一个字符串并返回一个整数。 它还可以传入第二个参数，指定了字符串中数字的基数。 基数可以是 2 到 36 之间的整数。

函数调用如下所示：

parseInt(string, radix);
这是一个示例：
```html
<script>
const a = parseInt("11", 2);
</script>
```
变量 radix 表示 11 是在二进制系统中。 这个示例将字符串 11 转换为整数 3。
## 使用三元运算符
条件运算符（ conditional operator,）（也称为三元运算符（ ternary operator））的就像写成一行的 if-else 表达式

语法是：a ? b : c, where a 是条件，当条件返回 true 的时候运行代码 b，当条件返回 false 的时候运行代码 c。

以下函数使用 if/else 语句来检查条件：
```html
<script>
function findGreater(a, b) {
  if(a > b) {
    return "a is greater";
  }
  else {
    return "b is greater or equal";
  }
}
</script>
```
这可以使用三元运算符重写：
```html
<script>
function findGreater(a, b) {
  return a > b ? "a is greater" : "b is greater or equal";
}
</script>
```
## 使用多个三元运算符
你也可以将多个运算符串联在一起以检查多种条件。

下面的函数使用 if，else if 和 else 语句来检查多个条件：
```html
<script>
function findGreaterOrEqual(a, b) {
  if (a === b) {
    return "a and b are equal";
  }
  else if (a > b) {
    return "a is greater";
  }
  else {
    return "b is greater";
  }
}
</script>
```
以上函数可以使用多个三元运算符重写：
```html
<script>
function findGreaterOrEqual(a, b) {
  return (a === b) ? "a and b are equal" 
    : (a > b) ? "a is greater" 
    : "b is greater";
}
</script>
```
如上文所示，对多个三元运算符进行每个条件都是单独一行的格式化被认为是最佳做法。 使用多个三元运算符而没有适当的缩进可能会使您的代码难以理解。 例如：
```html
<script>
function findGreaterOrEqual(a, b) {
  return (a === b) ? "a and b are equal" : (a > b) ? "a is greater" : "b is greater";
}
</script>
```
## 使用递归创建一个倒计时
现在来学习一个更复杂的函数，函数返回一个从 1 到传递给函数的指定数字的连续数字数组。

会有一个 base case。 base case 告诉递归函数什么时候不再需要调用其自身。 这是简单 情况，返回得到的值。 还有 recursive call，继续用不同的参数调用自身。 如果函数无误，一直执行直到 base case 为止。

比如，如果想写一个递归函数，返回一个数字 1 到 n 的连续数组。 这个函数需要接收一个参数 n 代表最终数字。 然后会持续的调用自身，传入一个比 n 更小的值一直到传入的值是 1 为止。 函数如下：
```html
<script>
function countup(n) {
  if (n < 1) {
    return [];
  } else {
    const countArray = countup(n - 1);
    countArray.push(n);
    return countArray;
  }
}
console.log(countup(5));
</script>
```
值 [1, 2, 3, 4, 5] 将显示在控制台中。

起初，这似乎是违反直觉的，因为 n 的值递减，但是最终数组中的值却递增。 之所以发生这种情况，是因为在递归调用返回之后，才调用 push。 在将 n pushed 进数组时，countup(n - 1) 已经调用赋值成功并返回了 [1, 2, ..., n - 1]。