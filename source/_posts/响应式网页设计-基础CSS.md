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