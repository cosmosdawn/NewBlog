---
title: Canvas
---

#### 栅格
在开始画图之前，需要了解下画布栅格和坐标空间。canvas元素默认被网格所覆盖。通常来说网格中的一个单元相当于canvas元素中的一像素。栅格的起点为左上角（坐标为（0,0））。所有元素的位置都相对于原点定位。

#### 绘制矩形
不同于SVG，HTML中的元素canvas只支持一种原生的图形绘制：矩形。
三种方式绘制矩形：

`fillRect(x, y, width, height)  //绘制一个填充的矩形`
`strokeRect(x, y, width, height)  //绘制一个矩形的边框`
`clearRect(x, y, width, height)  //清除指定矩形区域，让清除部分完全透明。
`

上述方法中，x y分别指定了在canvas画布上所绘制矩形的左上角的坐标。
width和height设置了矩形的尺寸。
以上的三个函数绘制之后会马上显现在canvas上，即时生效。

#### 绘制路径
* 首先需要创建路径起始点
* 然后使用画图命令画出路径
* 闭合路径
* 一旦路径生成就可以通过描边或者填充区域来渲染图形


#### Path2D对象
为了简化代码和提高性能，path2的对象已经可以在较新的浏览器中使用，用来缓存或者记录绘制命令，这样就可以快速的回顾路径。`Path2D()`函数，将会返回一个新初始化的Path2D对象（可将一个路径作为变量–创建一个他的副本，或者将一个包含svg path数据的字符串作为变量）

`new Path2D();   //空的Path对象`
`new Path2D(path) // 克隆Path对象`
`new Path2D(d);     //从svg建立Path对象`

所有的路径方法比如 moveTo, rect, arc 或 quadraticCurveTo等，如我们前面见过的，都可以在Path2D中使用。
Path2D API 添加了 addPath作为将path结合起来的方法。当你想要从几个元素中来创建对象时，这将会很实用。比如：

`Path2D.addPath(path [, transform])`
添加一条路径到当前路径（可能添加了一个变换矩阵）

#### 使用svg paths
新的path2d api有另一个强大的特点，就是使用svg path data来初始化canvas上的路径。这将使你获取路径时可以以SVG或canvas的方式来重用它们。

`var p = new Path2D("M10 10 h 80 v 80 h -80 z")`

上面一段svg路径的意思是： 现将路径移动到点(M10 10),然后再水平移动80个单位(h 80),然后下移80个单位(v 80),接着左移80个单位(h -80),再回到起点处(z)

#### 色彩Colors
fillStyle = color 设置图形的填充颜色
strokeStyle = color 设置图形轮廓的颜色
color 可以是表示 CSS 颜色值的字符串，渐变对象或者图案对象。我们迟些再回头探讨渐变和图案对象。默认情况下，线条和填充颜色都是黑色（CSS 颜色值 #000000）。

注意： 一旦您设置了 strokeStyle 或者 fillStyle 的值，那么这个新值就会成为新绘制的图形的默认值。如果你要给每个图形上不同的颜色，你需要重新设置 fillStyle 或 strokeStyle 的值。

您输入的应该是符合 CSS3 颜色值标准 的有效字符串。下面的例子都表示同一种颜色。

`// 这些 fillStyle 的值均为 '橙色'
ctx.fillStyle = "orange";
ctx.fillStyle = "#FFA500";
ctx.fillStyle = "rgb(255,165,0)";
ctx.fillStyle = "rgba(255,165,0,1)";`












