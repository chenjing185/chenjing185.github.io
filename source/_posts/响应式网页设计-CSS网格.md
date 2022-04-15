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
## 使用 grid-row 来控制空间大小
和设置一个网格项占用多列类似，你也可以设置它占用多行。 你可以使用 grid-row 属性来定义一个网格项开始和结束的水平线。
示例如下：
```
grid-row: 1 / 3;
```
## 使用 justify-self 水平对齐项目
在 CSS 网格中，每个网格项的内容分别位于被称为单元格（cell）的框内。 你可以使用网格项的 justify-self 属性，设置其内容的位置在单元格内沿水平轴的对齐方式。 默认情况下，这个属性的值是 stretch，这将使内容占满整个单元格的宽度。 该 CSS 网格属性也可以使用其他的值：

1. start：使内容在单元格左侧对齐
2. center：使内容在单元格居中对齐
3. end：使内容在单元格右侧对齐

## 使用 align-self 垂直对齐项目
正如能设置网格项沿水平方向的对齐方式一样，我们也可以设置网格项沿竖直方向的对齐方式。 为此，我们可以对网格项使用 align-self 属性来实现。 适用于 justify-self 属性的属性值同样也可用于这个属性。
## 使用 justify-items 水平对齐所有项目
有时你想让 CSS 网格中的网格项共享对齐方式。 你可以像之前学习的那样分别设置它们的对齐方式，也可以对网格容器使用 justify-items 使它们一次性沿水平轴对齐。 这个属性能接受我们在之前两个挑战中学到的所有值作为属性值，但与之前不同的是，它会将网格中 所有 的网格项按所设置的方式对齐。
## 使用 align-items 垂直对齐所有项目
对网格容器使用 align-items 属性可以让网格中所有的网格项沿竖直方向对齐。
## 将网格划分为区域模板
你可以将网格中的一些单元格组合成一个区域（area），并为该区域指定一个自定义名称。 可以通过给容器加上 grid-template-areas 来实现：
```
grid-template-areas:
  "header header header"
  "advert content content"
  "advert footer footer";
```
上面的代码将网格单元格分成四个区域：header、advert、content 和 footer。 每个单词代表一个单元格，每对引号代表一行。
## 使用 grid-area 属性将项目放置在网格区域中
像上一个挑战那样，在为网格添加区域模板后，可以通过引用你所定义的区域的名称，将元素放入相应的区域。 为此，你需要对网格项使用 grid-area：
```
.item1 {
  grid-area: header;
}
```
这样，class 为 item1 的网格项就被放到了 header 区域里。 在这种情况下，该项目将使用整个顶行，因为该整行被命名为 header 区域。
## 使用 grid-area 创建区域模板
我们在上一次挑战中学到的 grid-area 属性还有另一种使用方式。 如果网格中没有定义区域模板，你也可以像这样为它添加一个模板：
```
item1 { grid-area: 1/1/2/4; }
```
这里使用了你之前学习的网格线编号来定义网格项的区域。 上例中数字代表这些值：
```
grid-area: horizontal line to start at / vertical line to start at / horizontal line to end at / vertical line to end at;
```
因此，示例中的网格项将占用第 1 条水平网格线（起始）和第 2 条水平网格线（终止）之间的行，及第 1 条垂直网格线（起始）和第 4 条垂直网格线（终止）之间的列。
## 使用 repeat 函数减少重复
使用 grid-template-columns 或 grid-template-rows 定义网格结构时，你需要为添加的每一行或每一列都输入一个值。

如果一个网格共有 100 行且每行高度相同， 那我们就需要输入 100 个值，这显然不太实际。 为此，更好的方式是使用 repeat 方法指定行或列的重复次数，后面加上逗号以及需要重复的值。

以下为添加 100 行网格的例子，每行高度均为 50px：
```
grid-template-rows: repeat(100, 50px);
```
你还可以用 repeat 方法重复多个值，并在定义网格结构时与其他值一起使用。 比如：
```
grid-template-columns: repeat(2, 1fr 50px) 20px;
```
效果相当于：
```
grid-template-columns: 1fr 50px 1fr 50px 20px;
```
> 注意： 1fr 50px 重复了两次，后面跟着 20px。

## 使用 minmax 函数限制项目大小
此外，内置函数 minmax 也可用于设置 grid-template-columns 和 grid-template-rows 的值。 它的作用是在网格容器改变大小时限制网格项的大小。 为此，你需要指定网格项允许的尺寸范围。 例如：
```
grid-template-columns: 100px minmax(50px, 200px);
```
在上面的代码中，我们通过 grid-template-columns 添加了两列，第一列宽度为 100px，第二列宽度最小值是 50px，最大值是 200px。
## 使用 auto-fill 创建弹性布局
repeat 方法带有一个名为自动填充（auto-fill）的功能。 它的功能是根据容器的大小，尽可能多地放入指定大小的行或列。 你可以通过结合 auto-fill 和 minmax 来更灵活地布局。
```
repeat(auto-fill, minmax(60px, 1fr));
```
上面的代码效果是这样：首先，列的宽度会随容器大小改变。其次，只要容器宽度不足以插入一个宽为 60px 的列，当前行的所有列就都会一直拉伸。
> 注意： 如果容器宽度不足以将所有网格项放在同一行，余下的网格项将会移至新的一行。

## 使用 auto-fit 创建弹性布局
auto-fit 效果几乎和 auto-fill 一样。 不同点仅在于，当容器的大小大于各网格项之和时，auto-fill 会持续地在一端放入空行或空列，这样就会使所有网格项挤到另一边；而 auto-fit 则不会在一端放入空行或空列，而是会将所有网格项拉伸至合适的大小。

> 注意：如果容器宽度不足以将所有网格项放在同一行，余下的网格项将会移至新的一行。

## 使用媒体查询创建响应式布局
将 CSS 网格与使用媒体查询结合使用，如使用媒体查询重新排列网格区域、更改网格尺寸以及重新排列网格项位置，我们可以让制作出的网站更具响应性。

在右侧的预览区中，当网页可视区域的宽不小于 300px 时，列数从 1 变为 2。 并且，广告（advertisement）区域会完全占据左列。
```
@media (min-width: 400px){
    .container{
      grid-template-areas:
      /* 只修改这一行下面的代码 */
        "header header"
        "advert content"
        "footer footer";
      /* 只修改这一行上面的代码 */
    }
  }
```
## 在网格中创建网格
将元素转换为网格只会影响其子元素（即直接后代元素，英文为 direct descendants。意思是一个元素的所有后代元素中，父级元素为该元素的所有元素）。 因此，如果我们把某个子元素设置为网格，就会得到一个嵌套的网格。

例如，如果我们设置 class 为 item3 的元素的 display 和 grid-template-columns 属性，就会得到一个嵌套的网格。
```
.item3 {
    background: PaleTurquoise;
    grid-area: content;
    /* 只修改这一行下面的代码 */
    display: grid;
    grid-template-columns: auto 1fr;
    /* 只修改这一行上面的代码 */
  }
```