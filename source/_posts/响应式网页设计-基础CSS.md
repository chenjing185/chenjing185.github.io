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

当你输入 ```<h2 style="color: red;">CatPhotoApp</h2>```，就可以用行内 CSS 设置 h2 元素的样式。

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
可以看到，我们在```<style>```样式声明区域里，创建了一个名为blue-text的class选择器。 你可以这样将 class 应用于 HTML 元素：```<h2 class="blue-text">CatPhotoApp</h2>```。 注意在CSS style元素里，class 名以一个句点开头。 在HTML元素的class属性中，class 名的开头没有句点。
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
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
现在可以在 CSS 中使用 Lobster 字体，并像下面一样使用 Lobster 作为 FAMILY_NAME：
```
font-family: FAMILY_NAME, GENERIC_NAME;
```
GENERIC_NAME 是可选的，它用来指明在其他字体不可用时的后备字体。
字体名区分大小写，并且如果字体名含有空格，则在声明时需要用引号包起来。 例如，使用 "Open Sans" 字体需要添加引号，而 Lobster 则不需要。

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
### 用 border-radius 添加圆角边框
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

