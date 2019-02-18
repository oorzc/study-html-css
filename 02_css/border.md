
## border-style属性设置一个元素的四个边框的样式。此属性可以有一到四个值。
实例:
![](http://qiniu.sponges.cn/201802091830_149.png?imageView2/0/w/880/h/680)
border-style:dotted solid double dashed;
上边框是点状
右边框是实线
下边框是双线
左边框是虚线

##  double的妙用
![](http://qiniu.sponges.cn/201802091749_434.png)

* 绘制菜单图形

![](http://qiniu.sponges.cn/201802091751_729.png)
![](http://qiniu.sponges.cn/201802091753_312.png)

```html
<div class="a"></div>
.a{
width:40px; height: 6px;
border-top:18px double;
border-bottom:6px solid;
}
```

## border-color
不设置默认为文本颜色 使用hover 改变字体颜色boder 也同样变化
![](http://qiniu.sponges.cn/201802091842_366.png?imageView2/0/w/880/h/680)


## background-position
background-position是相对于左上角，且不把border计算在内，
因此，可以用border-right设置成想要元素距右多远的值，再设为透明，然后再设置background-position。
例如:border-right:1px solid transparent;background-position:100% 40px;
![](http://qiniu.sponges.cn/201802091845_262.png?imageView2/0/w/880/h/680)

## border-image边框图片属性
```
    /* 边框图片的路径*/
    border-image-source: url("images/border.png");

    /* 图片边框的裁剪*/
    border-image-slice: 27;
    /*图片边框的宽度*/
    border-image-width: 27px;
    /*边框图片的平铺*/
    /* repeat :正常平铺 但是可能会显示不完整*/
    /*round: 平铺 但是保证 图片完整*/
    /*stretch: 拉伸显示*/
    border-image-repeat: stretch;
```

图片切割

![](http://qiniu.sponges.cn/201803081027_141.jpg?imageView2/0/w/880/h/680)

可以理解为它是一个切片工具，会自动把用做边框的图片切割。怎么切割呢？为了方便理解，做了一张特殊的图片，由9个矩形（70*70像素）拼成的一张图（210*210像素），并标注好序号，像传说中的九宫图，如下：

![](http://qiniu.sponges.cn/201803081031_359.png?imageView2/0/w/880/h/680)

![](http://qiniu.sponges.cn/201803081032_425.png?imageView2/0/w/880/h/680)

![](http://qiniu.sponges.cn/201803081034_485.png?imageView2/0/w/880/h/680)