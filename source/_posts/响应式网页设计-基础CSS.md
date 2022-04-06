---
title: 响应式网页设计-基础CSS
date: 2022-04-03 16:15:59
categories:
- 响应式网页设计
tags:
- CSS
toc: true
readmore: true
sticky: 0
comments: true
---

CSS（级联样式表）告诉浏览器如何显示你在 HTML 中写入的文本和其他内容。你可以使用 CSS 控制 HTML 元素的颜色、字体、大小、间距等许多属性。

<!-- more -->
## 修改文本的颜色。
我们通过修改 h2 元素的 style 属性来改变文本颜色。
我们需要修改 color 属性值。
以下是将 h2 元素设置为蓝色的方法：
```html
<h2 style="color: blue;">CatPhotoApp</h2>
```
请注意,需要在内联 style 声明末尾加上;
## 使用元素选择器来设置元素的样式
在 CSS 中，页面样式的属性有几百个，你可以用来改变元素在页面上的外观。

当你输入 `<h2 style="color: red;">CatPhotoApp</h2>`，就可以用行内 CSS 设置 h2 元素的样式。

这是指定元素样式的一种方法，但有一个更好的方法来应用 CSS。

在代码的顶部，创建一个 style 声明区域，如下方所示：
```html
<style>
</style>
```
在样式声明区域内，可以为所有 h2 元素创建一个 CSS selector。 如果想让所有 h2 元素在变成红色，可以添加下方的样式规则：
```html
<style>
  h2 {
    color: red;
  }
</style>
```
请注意，每个元素的样式规则都应该有开始和结束大括号{和}。 还需要确保元素的样式定义在开始和结束样式标签之间。 你需要确保所有样式规则位于花括号之间，并且每条样式规则都以分号结束。
## 使用 class 选择器设置元素的样式
CSS 的 class 具有可重用性，可应用于各种 HTML 元素。
一个 CSS class 声明示例如下所示：
```html
<style>
  .blue-text {
    color: blue;
  }
</style>
```
可以看到，我们在`<style>`样式声明区域里，创建了一个名为blue-text的class选择器。 你可以这样将 class 应用于 HTML 元素：`<h2 class="blue-text">CatPhotoApp</h2>`。 注意在CSS style元素里，class 名以一个句点开头。 在HTML元素的class属性中，class 名的开头没有句点。
## 更改元素的字体大小
字体大小由 font-size 属性控制，如下所示：
```html
h1 {
  font-size: 30px;
}
```
## 元素的字体族名
### 设置元素的字体族名
通过 font-family 属性，我们可以设置元素里的字体族名。
如果你想将 h2 元素的字体设置为 sans-serif，可以这样写：
```html
h2 {
  font-family: sans-serif;
}
```

### 引入谷歌字体
在我们的网站上，除了使用系统提供的默认字体以外，我们也可以使用自定义字体。 网络上有很多字体库。 在这个例子中，我们将使用 Google 字体库。
Google 字体库是一个免费的 Web 字体库，我们只需要在 CSS 里设置字体的 URL 即可使用。
要引入 Google Font，你需要从 Google Fonts 上复制字体的 URL，并粘贴到你的 HTML 里面。 在这个挑战中，我们需要引入 Lobster 字体。 因此，请复制以下代码段，并粘贴到代码编辑器顶部，即放到 style 标签之前。
`<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">`
现在可以在 CSS 中使用 Lobster 字体，并像下面一样使用 Lobster 作为 FAMILY_NAME：
```
font-family: FAMILY_NAME, GENERIC_NAME;
```
GENERIC_NAME是可选的，它用来指明在其他字体不可用时的后备字体。
字体名区分大小写，并且如果字体名含有空格，则在声明时需要用引号包起来。 例如，使用 "Open Sans" 字体需要添加引号，而Lobster则不需要。

### 字体如何优雅降级
所有浏览器都有几种默认字体， 包括monospace、serif 和sans-serif。
在字体不可用的时候，你可以告诉浏览器通过“降级”去使用其他字体。
如果你想将一个元素的字体设置成 Helvetica，但当 Helvetica 不可用时，降级使用 sans-serif 字体，那么可以这样写：
```html
p {
  font-family: Helvetica, sans-serif;
}
```
通用字体名不区分大小写。 同时，也不需要使用引号，因为它们是 CSS 中的关键字。
## 调整图片的大小
CSS 的 width 属性可以控制元素的宽度。 和设置文本字号一样，我们会以 px（像素）为单位来设置图片的宽度。
例如，如果你想创建一个叫 larger-image 的 CSS class，来控制 HTML 元素的宽度为 500px，就可以这样写：
```html
<style>
  .larger-image {
    width: 500px;
  }
</style>
```
## 元素添加边框
### 在元素周围添加边框
CSS 边框具有 style、color、width 属性。
假如我们要将一个 HTML 元素边框设置为 5px 的红色实线边框，我们可以这样做：
```html
<style>
  .thin-red-border {
    border-color: red;
    border-width: 5px;
    border-style: solid;
  }
</style>
```

### 用border-radius添加圆角边框
边框的四个角看起来很尖锐， 我们可以使用border-radius属性来让它变得圆润。
```html
<style>
	.thick-green-border {
		border-color: green;
		border-width: 10px;
		border-style: solid;
		border-radius: 10px
	}
</style>
```

### 用border-radius制作圆形图片
除像素外，你也可以使用百分比来指定border-radius的值。
```html
<style>
	.thick-green-border {
		border-color: green;
		border-width: 10px;
		border-style: solid;
		border-radius: 50%
	}
</style>
```
## 给div元素添加背景色
background-color 属性可以设置元素的背景颜色。
如果想将一个元素的背景颜色改为 green，可以在style里面这样写：
```
.green-background {
  background-color: green;
}
```
## 元素的id
除了 class 属性，每一个 HTML 元素都有一个 id 属性。
使用 id 有几个好处：你可以通过 id 选择器来改变单个元素的样式。在稍后的课程中，你还会了解到如何在 JavaScript 里面用它来选择和操作元素。
根据规范，id 属性应是唯一的。 尽管浏览器并非必须执行这条规范，但这是广泛认可的最佳实践。 因此，请不要给多个元素设置相同的 id。
设置 h2 元素的 id 为 cat-photo-app 的代码如下：
```html
<h2 id="cat-photo-app">
```
## 使用id属性来设定元素的样式
通过id属性，你可以做一些很酷的事情。就像class一样，你可以使用CSS来设置他们的样式。
不过，id不可以重复，它只能作用于一个元素上。 如果一个元素同时应用了class和id，且两者设置的样式有冲突，会优先应用 id 中所设置的样式。
选择id为cat-photo-element的元素，并设置它的背景颜色为绿色。 可以在style标签里这样写：
```
#cat-photo-element {
  background-color: green;
}
```
注意在 style 标签里，声明 class 的时候必须在名字前插入.符号。同样，在声明 id 的时候，也必须在名字前插入#符号。
## 调整元素的内边距
所有的 HTML 元素都是以矩形为基础。每个 HTML 元素所占有的矩形空间由这三个重要的属性来控制：内边距padding、外边距margin 、边框border。padding用来控制着元素内容与border之间的空隙大小。
### 给元素的每一侧添加不同的内边距
有时候，你会想给一个元素每个方向的 padding 都设置一个特定的值
CSS 允许你使用 padding-top、padding-right、padding-bottom、padding-left 属性来设置四个不同方向的 padding 值。
### 使用顺时针标记指定元素的内边距
如果不想每次都要分别声明 padding-top、padding-right、padding-bottom、padding-left 属性，可以把它们汇总在一行里面一并声明，像是这样：
```
padding: 10px 20px 10px 20px;
```
这四个值按顺时针排序：上、右、下、左，并且设置的效果等同于分别声明每一个方向的内边距。
## 调整元素的外边距
外边距 margin 用来控制元素的边框与其他元素之间的 border 距离。
### 给元素添加负外边距
元素的 margin（外边距） 用来控制元素 border（边框） 与其周围元素之间的距离大小。
如果你把元素的 margin 设置为负值，元素会变得占用更多空间。
### 给元素的每一侧添加不同的外边距
有时候，你会想给一个元素每个方向的 margin 都设置成一个特定的值。
CSS 允许你使用 margin-top、margin-right、margin-bottom、margin-left 属性来设置四个不同方向的 margin 值。
### 使用顺时针标记指定元素的外边距
同样，每个方向的外边距值可以在一行里面汇总声明，而无需分别通过 margin-top、margin-right、margin-bottom、margin-left 分别声明，比如：
```
margin: 10px 20px 10px 20px;
```
这四个值按顺时针排序：上、右、下、左，并且设置的效果等同于分别声明每一个方向的外边距值。
## 使用属性选择器来设置元素的样式
我们已经通过设置元素的 id 和 class 来显示想要的样式。 这就是 ID 选择器和 Class 选择器。 另外，也还有其他的 CSS 选择器可以让我们给特定的元素设置样式。
属性选择器使用特定的属性值来匹配和设置元素样式。 例如，下面的代码会改变所有 type 为 radio 的元素的外边距。
```
[type='radio'] {
  margin: 20px 0px 20px 0px;
}
```
## 理解绝对单位与相对单位
设置元素的内边距和外边距的 px 值，即像素。 像素是一个长度单位，它告诉浏览器应该如何调整元素的大小和位置。 其实除了 px，CSS 也有其他单位供我们使用。
单位长度的类型可以分成 2 种：相对和绝对。 绝对单位与长度的物理单位相关。 例如，in 和 mm 分别代表着英寸和毫米。 绝对长度单位会接近屏幕上的实际测量值，不过不同屏幕的分辨率会存在差异，这就可能会造成误差。
相对单位长度，比如 em 和 rem，它们的实际值会依赖其他长度的值而决定。 比如 em 的大小基于元素字体的字体大小。 如果使用它来设置 font-size 值，它的值会跟随父元素的 font-size 值来改变。
Note: 有些单位长度选项是相对视窗大小来改变值的， 这种设定符合响应式网页设计的原则。
## 给 HTML 的 body 元素添加样式
每一个 HTML 页面都有一个 body 元素。
我们可以通过设置 background-color 的属性值为 黑色，来证明 body 元素的存在。
请将以下代码添加到 style 标签里面：
```
body {
  background-color: black;
}
```
## 从 body 元素继承样式
我们已经证明每一个 HTML 页面都含有 body 元素，我们也可以在 body 元素上使用 CSS 样式。
设置 body 元素样式的方法跟设置其他 HTML 元素样式的方式一样，并且其他元素也会继承 body 中所设置的样式。
## 样式中的优先级
有时候，HTML 元素的样式会跟其他样式发生冲突。就像 h1 元素不能同时设置绿色和粉色两种颜色。
1. Class 选择器的优先级高于继承样式
2. ID 选择器优先级高于 Class 选择器
3. 内联样式的优先级高于 ID 选择器
4. Important 的优先级最高,例如`color: red !important;`
## 颜色
### 使用十六进制编码获得指定颜色
你知道在 CSS 里面还有其他方式来代表颜色吗？ 其中一个方法叫十六进制编码，简称 hex。
日常生活中，我们使用的计数方法一般是 decimals，或十进制，即使用数字 0 到 9 来表示。 而 Hexadecimals（或 hex）基于 16 位数字， 它包括 16 种不同字符。 像十进制一样，0-9 的符号代表 0 到 9 的值。 然后，A、B、C、D、E、F 代表 10 至 15 的值。 总的来说，0 到 F 在十六进制里代表数字，总共有 16 个值。 你可以在此处找到更多关于十六进制信息。
在 CSS 里面，我们可以使用 6 个十六进制的数字来代表颜色，每两个数字控制一种颜色，分别是红（R）、绿（G）、蓝（B）。 例如，#000000 代表黑色，同时也是最小的值。 你可以在此处找到更多关于 RGB 颜色系统的信息。
```
body {
  color: #000000;
}
```
### 使用十六进制编码混合颜色
十六进制编码使用 6 个十六进制字符来表示颜色，两个字符为一组，分别代表红（R）、绿（G）、蓝（B）。
通过三原色（红、绿、蓝），我们可以创建 1600 万种不同颜色。
例如，橘色是纯红色混合一些绿色而成，其中没有蓝色。 在十六进制编码里面，它可以写成 #FFA500。
0 是十六进制里面最小的数字，表示没有颜色。
F 是十六进制里面最大的数字，有最高的亮度。
### 使用缩写的十六进制编码
许多人对超过 1600 万种颜色感到不知所措， 并且很难记住十六进制编码。 幸运的是，你可以使用缩写形式。
例如，红色的 #FF0000 十六进制编码可以缩写成 #F00。 在这种缩写形式里，三个数字分别代表着红（R）、绿（G）、蓝（B）三原色。
这样，颜色的数量减少到了大约 4000 种。 且在浏览器里 #FF0000 和 #F00 是完全相同的颜色。
### 使用 RGB 值为元素上色
RGB 值是在 CSS 中表示颜色的另一种方法。
黑色的 RGB 值：`rgb(0, 0, 0)`
白色的 RGB 值：`rgb(255, 255, 255)`
RGB 值与我们之前学到的十六进制编码不同。RGB 值不需要用到 6 位十六进制数字，而只需要指定每种颜色的亮度大小，数值范围从 0 到 255。
如果我们稍微计算一下，就不难发现这两种表示方式本质上是等价的。在十六进制编码中，我们用两个十六进制数表示一个颜色；这样，每种颜色都有 16 * 16（即 256）种可能。 所以，RGB 从零开始计算，与十六进制代码的值的数量完全相同。
下面是通过使用 RGB 值设置背景颜色为橘色的例子：body。
```
body {
  background-color: rgb(255, 165, 0);
}
```
### 使用 RGB 混合颜色
就像使用十六进制编码一样，你可以通过不同值的组合，来混合得到不同的 RGB 颜色。例如:
| 颜色 | RGB |
|:----:|:----:|
| 蓝色 | rgb(0, 0, 255) |
| 红色 | rgb(255, 0, 0) |
| 淡紫色 | rgb(218, 112, 214) |
| 赭黄色 | rgb(160, 82, 45) |
## CSS变量
### 创建一个自定义的 CSS 变量
为创建一个 CSS 变量，你只需要在变量名前添加两个连字符号，并为其赋值即可，例子如下：
```
--penguin-skin: gray;
```
这样就会创建一个 --penguin-skin 变量，它的值为 gray。 现在你可以在你的 CSS 中的其他地方使用这个变量来改变其他属性的值为灰色。
### 使用一个自定义的 CSS 变量
创建变量后，CSS 属性可以通过调用变量名来使用它对应的值。
```
background: var(--penguin-skin);
```
因为引用了 --penguin-skin 变量的值，使用了这个样式的元素背景颜色会是灰色。 请注意，除非变量名称完全匹配，否则将不会应用样式。
### 给 CSS 变量设置备用值
使用变量来作为 CSS 属性值的时候，可以设置一个备用值来防止由于某些原因导致变量不生效的情况。
注意： 备用值不是用于增强浏览器的兼容性，它也不适用于 IE 浏览器。 相反，它是用来让浏览器在找不到你的变量时可以显示一种颜色。
下面是操作方式：
```
background: var(--penguin-skin, black);
```
如果你的变量没有设置，这将会把背景设置为 black。 提示：这对调试代码也会很有帮助。
### 继承 CSS 变量
当创建一个变量时，变量会在创建变量的选择器里可用。 同时，在这个选择器的后代选择器里也是可用的。 这是因为 CSS 变量是可继承的，和普通的属性一样。
CSS 变量经常会定义在 :root 元素内，这样就可被所有选择器继承。
:root 是一个伪类选择器，它是一个能够匹配文档根元素的选择器，通常指的是 html 元素。 我们在 :root 里创建变量在全局都可用，即在任何选择器里都生效。
### 更改特定区域的变量
当你在 :root 里创建变量时，这些变量的作用域是整个页面。
然后，你可以通过在一个特定的选择器中再次设置这些变量来重写这些变量。
### 使用媒体查询更改变量
CSS 变量可以简化媒体查询的定义方式。
例如，当屏幕小于或大于媒体查询所设置的值，只要我们更新变量的值，那么使用了此变量的元素样式就都会更改。
```html
<style>
  :root {
    --penguin-size: 300px;
    --penguin-skin: gray;
    --penguin-belly: white;
    --penguin-beak: orange;
  }

  @media (max-width: 350px) {
    :root {
      /* 只修改这一行下面的代码 */
      --penguin-size: 200px;
      --penguin-skin: black;
      /* 只修改这一行上面的代码 */
    }
  }
</style>
```
## 通过浏览器降级提高兼容性
使用 CSS 时可能会遇到浏览器兼容性问题。 提供浏览器降级方案来避免潜在的问题会显得很重要。
当浏览器解析页面的 CSS 时，会自动忽视不能识别或者不支持的属性。 举个例子，如果使用 CSS 变量来指定站点的背景色，IE 浏览器由于不支持 CSS 变量而会忽略背景色。 此时，浏览器会尝试使用其它值。 但如果没有找到其它值，则会使用默认值，也就是没有背景色。
这意味着如果想提供浏览器降级方案，在声明之前提供另一个更宽泛的值即可。 这样老旧的浏览器会降级使用这个方案，新的浏览器会在后面的声明里覆盖降级方案。
我们使用了 CSS 变量来定义 .red-box 的背景色。 现在，我们通过在现有的声明之前添加另一个 background 声明，并将它的值设置为 red，来提升浏览器的兼容性。
```html
<style>
  :root {
    --red-color: red;
  }
  .red-box {
    background: red;
    background: var(--red-color);
    height: 200px;
    width:200px;
  }
</style>
<div class="red-box"></div>
```