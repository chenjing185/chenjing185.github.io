---
title: 响应式网页设计-基础HTML和HTML5
date: 2022-04-01 15:55:10
categories:
- 响应式网页设计
- freecodecamp
tags:
- HTML
- HTML5
toc: true
readmore: true
sticky: 100
comments: true
---

HTML 是一种标记语言，使用特殊的语法或标记来向浏览器描述网页的结构。HTML 元素由开始和结束标签构成，标签之间是文本内容。 不同的标签可以让文本内容以标题、段落、列表等形式展现。

<!-- more -->
大部分 HTML 元素都有一个开始标签和一个结束标签。
开始标签像这样：
```html
<h1>
```
结束标签像这样：
```html
</h1>
```
开始标签和结束标签的唯一区别就是结束标签多了一个斜杠。

## 标题标签: h1~h6
这些元素用来告诉浏览器网站的结构是什么样子。 h1 元素通常被用作主标题，h2 元素通常被用作副标题， 还有 h3、h4、h5、h6 元素，它们分别用作不同级别的标题。
```html
<h1></h1>
<h2></h2>
<h3></h3>
<h4></h4>
<h5></h5>
<h6></h6>
```

## 段落标签: p
p 元素是网站上段落文本的首选元素。 p 是“paragraph（段落）”的缩写。
```html
<p></p>
```

## 注释标签: 
```html
<!--注释文本-->
```

## 图片标签: img
你可以使用 img 元素来为你的网站添加图片，其中 src 属性指向图片的地址。
例如：
```html
<img src="https://www.freecatphotoapp.com/your-image.jpg">
```
注意：img 元素是没有结束标签的。所有的 img 元素 必须 有 alt 属性。 alt 的属性值有两个作用，第一个作用是让屏幕阅读器可以知晓图片的内容，这会对网页的可访问性有很大提升；另一个作用是当图片无法加载时，页面需要显示的替代文本。
注意： 如果图片是纯装饰性的，把 alt 的属性值设置为空是最佳实践。理想情况下，alt 属性不应该包含特殊字符，除非有特殊需要。

## 超链接标签: a
### 网页间的跳转 
你可以用 a（Anchor，简写为 a）来实现网页间的跳转。

a 需要一个 href 属性指向跳转的目的地。 同时，它还应有内容。 例如：
```html
<a href="https://www.freecodecamp.org">this links to freecodecamp.org</a>
```
浏览器将显示文本 this links to freecodecamp.org，这是一个可点击的链接。 你可以通过这个链接访问 https://www.freecodecamp.org。

### 网页内部的跳转
a（anchor）元素也可以用于创建内部链接，跳转到网页内的各个不同部分。
要创建内部链接，你需要将链接的 href 属性值设置为一个哈希符号 # 加上你想内部链接到的元素的 id，通常是在网页下方的元素。 然后你需要将相同的 id 属性添加到你链接到的元素中。 id 是描述网页元素的一个属性，它的值在整个页面中唯一。
例如当用户点击了 Contacts 链接，页面就会跳转到网页的 Contacts 区域。
```html
<a href="#contacts-header">Contacts</a>
...
<h2 id="contacts-header">Contacts</h2>
```
当用户点击 Contacts 链接时，他们将被带到带有 Contacts 标题元素的网页部分。

### 将a标签嵌套在段落中
你可以在其他文本元素内嵌套链接。
```html
<p>
  Here's a <a target="_blank" href="https://www.freecodecamp.org"> link to www.freecodecamp.org</a> for you to follow.
</p>
```
让我们来拆解一下这个例子。 通常，文本是被包裹在 p 元素内：
```html
<p> Here's a ... for you to follow. </p>
接下来是锚点元素 <a>（它需要结束标签 </a>）：
```html
<a> ... </a>
```
target 是锚点元素的一个属性，它用来指定链接的打开方式。 属性值 _blank 表示链接会在新标签页打开。 href 是锚点元素的另一个属性，它用来指定链接的 URL：
```html
<a href="https://www.freecodecamp.org" target="_blank"> ... </a>
```
a 元素内的文本 link to www.freecodecamp.org 叫作锚文本，会显示为一个可以点击的链接：
```html
<a href=" ... " target="...">link to freecodecamp.org</a>
```
此示例的最终输出结果是这样：
Here's a link to www.freecodecamp.org for you to follow.

### 链接占位符#
有时你想为网站添加一个 a 元素，但还不确定要将它链接到哪里。 可以将 href 属性的值替换为#，以此来创建链接占位符。例如: 
```html
<a href="#" target="..."></a>
```

### 给图片添加链接
你可以通过把元素嵌套进 a 里使其变成一个链接。如果我们要把图片嵌套进 a 元素， 可以这样写：
```html
<a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="Three kittens running towards the camera."></a>
```
如果把 a 的 href 属性值设置为 #，创建的是一个死链接（不跳转到其他画面）。

## 列表标签
### 无序列表
HTML 有一个特定的元素用于创建无序列表。
无序列表以 <ul> 开始，中间包含一个或多个 <li> 元素， 最后以 </ul> 结束。
例如:
```html
<ul>
  <li>milk</li>
  <li>cheese</li>
</ul>
```
会创建一个要点列表，包括 milk 和 cheese。

### 有序列表
HTML 中有用于创建有序列表的特定元素。
有序列表以 <ol> 开始，中间包含一个或多个 <li> 元素。 最后以 </ol> 结束。
例如:
```html
<ol>
  <li>Garfield</li>
  <li>Sylvester</li>
</ol>
```
将创建一个包含 Garfield 和 Sylvester 的编号列表。