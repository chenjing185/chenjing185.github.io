---
title: 响应式网页设计-基础HTML和HTML5
date: 2022-04-01 15:55:10
categories:
- 响应式网页设计
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
> 注意： 如果图片是纯装饰性的，把 alt 的属性值设置为空是最佳实践。理想情况下，alt 属性不应该包含特殊字符，除非有特殊需要。

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
无序列表以ul开始，中间包含一个或多个li元素， 最后以/ul结束。
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
有序列表以ol开始，中间包含一个或多个li元素。 最后以/ol结束。
例如:
```html
<ol>
  <li>Garfield</li>
  <li>Sylvester</li>
</ol>
```
将创建一个包含 Garfield 和 Sylvester 的编号列表。

## 输入框标签
input 输入框可以让你轻松获得用户的输入。你可以像这样创建一个文本输入框：
```html
<input type="text">
```
> 注意 input 输入框是没有结束标签的。

## 给输入框添加占位符文本
占位符文本是用户在 input 输入框中输入任何东西前的预定义文本。你可以像这样创建一个占位符：
```html
<input type="text" placeholder="this is placeholder text">
```
> 注意： 别忘了 input 元素是 "自闭和标签"，即不需要结束标签。

## 表单
### 创建表单
我们可以只通过 HTML 来实现发送数据给服务器的表单， 只需要给 form 元素添加 action 属性即可。例如：
```html
<form action="url-where-you-want-to-submit-form-data">
  <input>
</form>
```

### 给表单添加提交按钮
给表单添加一个 submit（提交）按钮。 点击提交按钮时，表单中的数据将会被发送到 action 属性指定的 URL 上。例如：
```html
<button type="submit">this button submits the form</button>
```

### 给表单添加一个必填字段
当你设计表单时，你可以指定某些字段为必填项（required），只有当用户填写了该字段后，才可以提交表单。
如果你想把文本输入框设置为必填项，在 input 元素中加上 required 属性就可以了，例如：
```html
<input type="text" required>
```

## 单选框和复选框
### 创建一组单选按钮
单选按钮是 input 选择框的一种类型。
每一个单选按钮都应该嵌套在它自己的 label（标签）元素中。 这样，我们相当于给 input 元素和包裹它的 label 元素建立起了对应关系。
所有关联的单选按钮应该拥有相同的 name 属性。 创建一组单选按钮，选中其中一个按钮，其他按钮即显示为未选中，以确保用户只提供一个答案。
下面是一个单选按钮的例子：
```html
<label> 
  <input type="radio" name="indoor-outdoor">Indoor 
</label>
```
最佳实践是在 label 元素上设置 for 属性，让其值与相关联的 input 单选按钮的 id 属性值相同。 这使得辅助技术能够在标签和相关的 input 元素之间建立关联关系。 例如：
```html
<input id="indoor" type="radio" name="indoor-outdoor">
<label for="indoor">Indoor</label>
```
我们也可以在 label 标签中嵌入 input 元素：
```html
<label for="indoor"> 
  <input id="indoor" type="radio" name="indoor-outdoor">Indoor 
</label>
```

### 创建一组复选框
复选框是 input 选择框的一种类型。
每一个复选框都应该嵌套在它自己的 label（标签）元素中。这样我们相当于给 input 元素和包裹它的 label 元素建立起了对应关系。所有关联的复选框应该拥有相同的 name 属性。
使得 input 与 label 关联的最佳实践是在 label 元素上设置 for 属性，让其值与相关联的 input 复选框的 id 属性值相同。
下面是一个复选框的例子：
```html
<label for="loving"><input id="loving" type="checkbox" name="personality"> Loving</label>
```

### 使用单选框和复选框的value属性
提交表单时，所选项的值会发送给服务端。 radio 和 checkbox 的 value 属性值决定了发送到服务端的实际内容。
例如：
```html
<label for="indoor">
  <input id="indoor" value="indoor" type="radio" name="indoor-outdoor">Indoor
</label>
<label for="outdoor">
  <input id="outdoor" value="outdoor" type="radio" name="indoor-outdoor">Outdoor
</label>
```
这里有两个 radio 单选框。 当用户提交表单时，如果 indoor 选项被选中，表单数据会包含：indoor-outdoor=indoor。 也就是所选项的 name 和 value 属性值。
如果没有指明 value 属性值，则会使用默认值做为表单数据提交，也就是 on。 在这种情况下，如果用户选中 "indoor" 选项然后提交表单，表单数据则会包含 indoor-outdoor=on。 这样的表单数据看起来不够直观，因此最好将 value 属性值设置为一些有意义的内容。

### 给单选按钮和复选框添加默认选中项
用 checked 属性把第一个复选框和单选按钮都设置为默认选中。
为此，只需将单词 checked 添加到 input 元素的内部。 例如:
```html
<input type="radio" name="test-name" checked>
```

## 元素嵌套
div 元素也叫内容划分元素，是一个包裹其他元素的通用容器。
它也是 HTML 中出现频率最高的元素。
和其他普通元素一样，你可以用<div>来标记一个 div 元素的开始，用 </div> 来标记一个 div 元素的结束。

## 声明HTML的文档类型
在文档的顶部，我们需要告诉浏览器网页所使用的 HTML 的版本。 HTML 是一个在不停发展的语言，大部分浏览器都支持 HTML 的最新标准，也就是 HTML5。 大部分主流浏览器都支持最新的 HTML5 规范。 但是一些陈旧的网页可能使用的是老版本的 HTML。
你可以通过 <!DOCTYPE ...> 来告诉浏览器页面上使用的 HTML 版本，"..." 部分就是版本号。 <!DOCTYPE html> 对应的就是 HTML5。
! 和大写的 DOCTYPE 是很重要的，尤其是对那些老的浏览器。 但 html 无论大写小写都可以。
所有的 HTML 代码都必须位于 html 标签中。 其中 <html> 位于 <!DOCTYPE html> 之后，</html> 位于网页的结尾。
这是一个网页结构的列子。 你的 HTML 代码会在两个 html 标签之间。
```html
<!DOCTYPE html>
<html>

</html>
```

## 定义HTML文档的head和body
html 的结构主要分为两大部分：head 和 body。 网页的描述应放入 head 标签， 网页的内容（向用户展示的）则应放入 body 标签。
比如 link、meta、title 和 style 都应放入 head 标签。
这是网页布局的一个例子：
```html
<!DOCTYPE html>
<html>
  <head>
    <meta />
  </head>
  <body>
    <div>
    </div>
  </body>
</html>
```