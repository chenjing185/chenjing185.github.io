---
title: 响应式网页设计-CSS网格
date: 2022-04-14 23:29:48
categories:
- 响应式网页设计
tags:
- CSS
- HTML
toc: true
readmore: true
sticky: 0
comments: true
---

CSS 网格是一个较新的标准，用于构建复杂的响应布局。它通过把 HTML 元素转换为具有行和列的网格容器，以便将子元素放置在所需要的位置。

<!-- more -->
## 创建你的第一个 CSS 网格
通过将属性 display 的值设为 grid，HTML 元素就可以变为网格容器。 通过前面的操作，你可以对该容器使用与 CSS 网格（CSS Grid）相关的属性。

> 注意： 在 CSS 网格中，父元素称为容器（container），它的子元素称为项（items）。
## 使用 grid-template-columns 添加多列
简单地添加一个网格元素并不会有任何明显的效果。 你还需要明确网格的结构。 在一个网格容器中使用 grid-template-columns 属性可以添加一些列，示例如下：
```
.container {
  display: grid;
  grid-template-columns: 50px 50px;
}
```
上面的代码会在网格容器中添加两列，宽度均为 50px。 grid-template-columns 属性值的个数表示网格的列数，每个值表示相应的列宽度。
## 使用 grid-template-rows 添加多行
在上面的示例中，你创建的网格会自动设置行数。 要手动调整行，请使用 grid-template-rows 属性，就像在上一个挑战中使用 grid-template-columns 属性一样。
## 使用 CSS 网格单位来更改列和行的大小
在 CSS 网格中，可以使用绝对单位（如 px）或相对单位（如 em）来定义行或列的大小。 下面的单位也可以使用：

* fr：设置列或行占剩余空间的比例，
* auto：设置列宽或行高自动等于它的内容的宽度或高度，
* %：将列或行调整为它的容器宽度或高度的百分比，
以下代码为右侧预览区中的效果：
```
grid-template-columns: auto 50px 10% 2fr 1fr;
```
这段代码添加了五个列。 第一列的宽与它的内容宽度相等；第二列宽 50px；第三列宽是它容器的 10%；最后两列，将剩余的宽度平均分成三份，第四列占两份，第五列占一份。
## 使用 grid-column-gap 创建多列之间的间距
目前为止，在你所创建的网格中，每列都相互紧挨着。 有时候你想要列之间有一个间距。 如果需要在列与列之间添加一些间距，我们可以使用 grid-column-gap：
```
grid-column-gap: 10px;
```
这会为我们创建的所有列之间都添加 10px 的空白间距。
## 使用 grid-row-gap 创建多行之间的间距
和上个挑战在两列之间添加间距一样，我们还可以用 grid-row-gap 设置行间距。
## 使用 grid-gap 为网格添加间距
grid-gap 属性是前两个挑战中出现的 grid-row-gap 和 grid-column-gap 的简写属性，它更方便使用。 如果 grid-gap 只有一个值，那么这个值表示行与行之间、列与列之间的间距均为这个值。 如果有两个值，那么第一个值表示行间距，第二个值表示列间距。

## 使用 grid-column 来控制空间大小
到目前为止，所有的讨论都是围绕网格容器的。 grid-column 属性是我们要讨论的，第一个用于网格项本身的属性。

网格中，假想的水平线和垂直线被称为线（lines）。 这些线在网格的左上角从 1 开始编号，垂直线向右、水平线向下累加计数。

这是一个 3x3 网格的线条：

![](https://cdn.jsdelivr.net/gh/chenjing185/chenjing185.github.io@latest/images/web/1.png)

列线1234行线1234
要设置一个网格项占据几列，你可以使用 grid-column 属性加上网格线条的编号来定义网格项开始和结束的位置。

示例如下：
```
grid-column: 1 / 3;
```
这会让网格项从左侧第一条线开始到第三条线结束，占用两列。