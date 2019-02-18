## Flex 布局
1. Flex 布局是什么？
```
        Flex 是 Flexible Box 的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性。
        任何一个容器都可以指定为 Flex 布局。

        .box{
            display: flex;
        }
        行内元素也可以使用 Flex 布局。

        .box{
        display: inline-flex;
        }
        Webkit 内核的浏览器，必须加上-webkit前缀。

        .box{
        display: -webkit-flex; /* Safari */
        display: flex;
        }
        注意，设为 Flex 布局以后，子元素的float、clear和vertical-align属性将失效。

        容器的属性
        flex-direction
        flex-wrap
        flex-flow
        justify-content
        align-items
        align-content
```

2.  flex-direction属性决定主轴的方向（即项目的排列方向）。
```
     .box {
        flex-direction: row | row-reverse | column | column-reverse;
    }

    row（默认值）：主轴为水平方向，起点在左端。
    row-reverse：主轴为水平方向，起点在右端。
    column：主轴为垂直方向，起点在上沿。
    column-reverse：主轴为垂直方向，起点在下沿。
```

3. 默认情况下，项目都排在一条线（又称"轴线"）上。flex-wrap属性定义，如果一条轴线排不下，如何换行。
    * nowrap（默认）：不换行。
    * wrap：换行，第一行在上方。
    * wrap-reverse：换行，第一行在下方。

4. justify-content属性定义了项目在主轴上的对齐方式。
```
     .box {
        justify-content: flex-start | flex-end | center | space-between | space-around;
    }

    flex-start（默认值）：左对齐
    flex-end：右对齐
    center： 居中
    space-between：两端对齐，项目之间的间隔都相等。
    space-around：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。
```

5. align-items属性定义项目在交叉轴上如何对齐。
```
        .box {
            align-items: flex-start | flex-end | center | baseline | stretch;
        }

        flex-start：交叉轴的起点对齐。
        flex-end：交叉轴的终点对齐。
        center：交叉轴的中点对齐。
        baseline: 项目的第一行文字的基线对齐。
        stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。
```

6.  (使用较少)align-content属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。
```
    .box {
        align-content: flex-start | flex-end | center | space-between | space-around | stretch;
    }
    flex-start：与交叉轴的起点对齐。
    flex-end：与交叉轴的终点对齐。
    center：与交叉轴的中点对齐。
    space-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
    space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
    stretch（默认值）：轴线占满整个交叉轴。
```

7. 以下属性设置子元素上：
```
        order 属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。
        flex-grow 属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。
        flex-shrink 属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。
        flex-basis 属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。
        flex 属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。
        align-self 属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的
        align-items属性，如果没有父元素，则等同于stretch。
        .item {
       	 align-self: auto | flex-start | flex-end | center | baseline | stretch;
         }
 ```