---
title: 响应式网页设计-CSS弹性盒子
date: 2022-04-13 09:24:22
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

Flexbox（弹性盒子）是最新版本的 CSS（即 CSS3）中引入的一种强大且兼容性好的布局方法。使用 flexbox，我们可以很容易地处理好页面上的元素布局，并创建可以自动缩小和放大的动态用户界面。

<!-- more -->
## 使用 display: flex 定位两个盒子
只要在一个元素的 CSS 中添加 display: flex;，就可以使用其它 flex 属性来构建响应式页面了。例如:
```
 #box-container {
    height: 500px;
    display: flex;
  }
```
## 使用 flex-direction 属性创建一个行
给元素添加 display: flex 属性可以让它变成 flex 容器， 然后可以让元素的项目排列成行或列。 只要给父元素添加 flex-direction 属性，并把属性值设置为以下可选值,即可达成可选值的效果.

flex-direction的可选值有:
1. row：横向从左到右排列（左对齐），默认的排列方式。
2. row-reverse：反转横向排列（右对齐，从后往前排，最后一项排在最前面。
3. column：纵向排列。
4. column-reverse：反转纵向排列，从后往前排，最后一项排在最上面。

```
#box-container {
    display: flex;
    height: 500px;
    flex-direction: column;
  }
```
## 使用 justify-content 属性对齐元素
flex 子元素有时不能充满整个 flex 容器， 所以我们经常需要告诉 CSS 以什么方式排列 flex 子元素，以及调整它们的间距。 幸运的是，我们可以通过 justify-content 属性的不同值来实现。 在介绍属性的可选值之前，我们要先理解一些重要术语。

回忆一下，如果把 flex 容器设为一个行，它的子元素会从左到右逐个排列； 如果把 flex 容器设为一个列，它的子元素会从上到下逐个排列。 子元素排列的方向被称为 main axis（主轴）。 对于行，主轴水平贯穿每一个项目； 对于列，主轴垂直贯穿每一个项目。
例子:
```
#box-container {
    background: gray;
    display: flex;
    height: 500px;
    justify-content: center;
  }
```
justify-content可选值包括：

* center: 即 flex 子元素在 flex 容器中居中排列。
* flex-start：从 flex 容器的起始位置开始排列项目。 对行来说是把项目移至左边， 对于列是把项目移至顶部。 如未设置 justify-content 的值，那么这就是默认值。
* flex-end：从 flex 容器的终止位置开始排列项目。 对行来说是把项目移至右边， 对于列是把项目移至底部。
* space-between：项目间保留一定间距地沿主轴居中排列。 第一个和最后一个项目被放置在容器边沿。 例如，在行中第一个项目会紧贴着容器左边，最后一个项目会紧贴着容器右边，然后其他项目均匀排布。
* space-around：与space-between相似，但头尾两个项目不会紧贴容器边缘，所有项目之间的空间均匀排布。
space-evenly：在 flex 项目之间均匀分配空间，在 flex 容器的任一端都有一个完整的空间。

## 使用 align-items 属性对齐元素
align-items 属性与 justify-content 类似。 回忆一下，justify-content 属性使 flex 子元素沿主轴排列。 行的主轴是水平线，列的主轴是垂直线。

Flex 容器中，与主轴垂直的叫做 cross axis（交叉轴）。 行的交叉轴是垂直的，列的交叉轴是水平的。

CSS 中的 align-items 属性用来定义 flex 子元素沿交叉轴的对齐方式。 对行来说，定义的是元素的上下对齐方式； 对列来说，是定义元素的左右对齐方式。
例子:
```
#box-container {
    background: gray;
    display: flex;
    height: 500px;
    align-items: center;
  }
```
align-items 的可选值包括：

* flex-start：从 flex 容器的起始位置开始对齐项目。 对行来说，把项目移至容器顶部； 对列来说，是把项目移至容器左边。
* flex-end：从 flex 容器的终止位置开始对齐项目。 对行来说，把项目移至容器底部； 对列来说，把项目移至容器右边。
* center：把项目居中放置。 对行来说，垂直居中（项目距离顶部和底部的距离相等）； 对列来说，水平居中（项目距离左边和右边的距离相等）。
* stretch：拉伸项目，填满 flex 容器。 例如，排成行的项目从容器顶部拉伸到底部。 如未设置align-items的值，那么这就是默认值。
* baseline：沿基线对齐。 基线是文本相关的概念，可以认为它是字母排列的下端基准线。

## 使用 flex-wrap 属性包裹一行或一列
CSS flexbox 具有将 flex 容器拆分为多行（或列）的功能。 默认情况下，flex 容器会调整项目大小，把它们都塞到一起。 对于行来说，所有项目都会在一条直线上。

不过，使用 flex-wrap 属性可以使项目换行展示。 这意味着多出来的子元素会被移到新的行或列。 换行发生的断点由子元素和容器的大小决定。
例子:
```
#box-container {
    background: gray;
    display: flex;
    height: 100%;
    flex-wrap: wrap;
  }
```
换行方向的可选值有这些：

* nowrap：默认值，不换行。
* wrap：如果排列以行为基准，就将行从上往下排列；如果排列以列为基准，就将列从左往右排列。
* wrap-reverse：如果排列以行为基准，就将行从下往上排列；如果排列以列为基准，就将列从右往左排列。

## 使用 flex-shrink 属性定义 flex 子元素的收缩规则
目前为止，提到的属性都是应用于 flex 容器（flex 子元素的父元素）的。 除此之外，flex 子元素也有很多实用属性。

首先介绍的是 flex-shrink 属性。 使用之后，如果 flex 容器太小，则子元素会自动缩小。 当容器的宽度小于里面所有子元素的宽度之和时，所有子元素都会自动压缩。

子元素的 flex-shrink 接受数值作为属性值。 数值越大，则该元素与其他元素相比会被压缩得更厉害。 比如，一个项目的 flex-shrink 属性值为 1，另一个项目的 flex-shrink 属性值为 3，那么后者相比前者会受到 3 倍压缩。
例子: 
```
#box-container {
    display: flex;
    height: 500px;
  }
#box-1 {
    background-color: dodgerblue;
    width: 100%;
    height: 200px;
    flex-shrink: 1;
  }
```
## 使用 flex-grow 属性定义 flex 子元素的增长系数
与 flex-shrink 相对的是 flex-grow。 你应该还记得，flex-shrink 会在容器太小时对子元素作出调整。 相应地，flex-grow 会在容器太大时对子元素作出调整。

例子与之前相似，如果一个项目的 flex-grow 属性值为 1，另一个项目的 flex-grow 属性值为 3，那么值为 3 的一个会较另一个扩大 3 倍。
例子: 
```
#box-container {
    display: flex;
    height: 500px;
  }
#box-1 {
    background-color: dodgerblue;
    height: 200px;
    flex-grow: 1;
  }
```
## 使用 flex-basis 属性设置元素的初始大小
flex-basis 属性定义了在使用 CSS 的 flex-shrink 或 flex-grow 属性对元素进行调整前，元素的初始大小。

flex-basis 属性的单位与其他表示尺寸的属性的单位一致（px、em、% 等）。 如果值为 auto，则项目的尺寸随内容调整。
```
#box-container {
    display: flex;
    height: 500px;
  }
#box-1 {
    background-color: dodgerblue;
    height: 200px;
    flex-basis: 10em;
  }
```
## 使用 flex 短方法属性
上面几个 flex 属性有一个简写方式。 flex-grow、flex-shrink 和 flex-basis 属性可以在 flex 中一并设置。

例如，flex: 1 0 10px; 会把项目属性设为 flex-grow: 1;、flex-shrink: 0; 以及 flex-basis: 10px;。

> 属性的默认设置是 flex: 0 1 auto;。

```
#box-container {
    display: flex;
    height: 500px;
  }
#box-1 {
    background-color: dodgerblue;
    flex: 2 2 150px;
    height: 200px;
  }
```
## 使用 order 属性重新排列子元素
order 属性告诉 CSS flex 容器里子元素的顺序。 默认情况下，项目排列顺序与源 HTML 文件中顺序相同。 这个属性接受数字作为参数，可以使用负数。

```
#box-container {
    display: flex;
    height: 500px;
  }
#box-1 {
    background-color: dodgerblue;
    order: 2;
    height: 200px;
    width: 200px;
  }
```
## 使用 align-self 属性
flex 子项目的最后一个属性是 align-self。 这个属性允许你调整单个子元素自己的对齐方式，而不会影响到全部子元素。 因为 float、clear 和 vertical-align 等调整对齐方式的属性都不能应用于 flex 子元素，所以这个属性显得十分有用。

align-self 可设置的值与 align-items 的一样，并且它会覆盖 align-items 所设置的值。

```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }
  #box-1 {
    background-color: dodgerblue;
    align-self: center;
    height: 200px;
    width: 200px;
  }

  #box-2 {
    background-color: orangered;
    align-self: flex-end;
    height: 200px;
    width: 200px;
  }
</style>
```