## 对于inline元素
1. padding影响水平尺寸  不影响垂直 但是影响背景色
2. inline水平元素的padding百分比值
    * 同样相对于宽度计算
    * 默认的高度宽度细节有差异
    * padding会断行
3. inline就算是空白元素，padding高和宽也不想等
 * 是因为：inline元素的垂直padding会让“幽灵空白节点”显现，也就是规范中的"strut"出现。

## 对于block元素
1. 即使是设了box-sizing:border-box;
 当padding增大到一定程度时，就会改变容器的宽高
 ![](http://qiniu.sponges.cn/201802222041_598.png?imageView2/0/w/680/h/480)
2. width:auto 或box-sizing:border-box时，元素尺寸不会改变，内容(骨架)收缩
![](http://qiniu.sponges.cn/201802222043_32.png?imageView2/0/w/680/h/480)

## padding的百分比是按照宽度进行计算的，padding不支持任何形式的负值
1.制作正方形的横幅，可以利用百分比padding为50%，
![](http://qiniu.sponges.cn/201802222047_965.png?imageView2/0/w/680/h/480)

## 其他padding相关
![](http://qiniu.sponges.cn/201802222054_925.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802222055_390.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802222055_289.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802222056_640.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802222057_164.png?imageView2/0/w/680/h/480)

## padding·绘制图形
1. 三道杠
![](http://qiniu.sponges.cn/201802222102_630.png?imageView2/0/w/680/h/480)
2. 白眼
![](http://qiniu.sponges.cn/201802222104_120.png?imageView2/0/w/680/h/480)

## padding 布局
1. 使用百分比单位构建固定比例布局结构（正方形）
2. 配合margin等高布局
![](http://qiniu.sponges.cn/201802222133_338.png?imageView2/0/w/680/h/480)
3. 两栏自适应效果
![](http://qiniu.sponges.cn/201802222135_888.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802222136_762.png?imageView2/0/w/680/h/480)
4. 1:1 自适应
> 参考https://codepen.io/crazyzhanyue/pen/zRgJaG
```css
    li{
        display: inline-block;
        float: left;
        width: 33.33%;
        box-sizing: border-box;
        margin-right: -1px;
    }
    .xx{
        padding-top: 100%;
        border: 1px solid red;
    }
```
