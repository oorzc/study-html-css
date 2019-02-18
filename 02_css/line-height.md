## line-height定义,又称行高
> line-height  两行文字之间基线（或中线，或顶线）之间的距离，不是指行间距

1. 不同的字体 基线位置也不一样
2. 不同的语言基线是不一样的
![](http://qiniu.sponges.cn/201802232200_949.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232155_140.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232156_704.png?imageView2/0/w/680/h/480)
* line-height为零，两行文字重合

* 通常我们说：line-height 可以使单行文本自动垂直居中（事实上并没有垂直居中，而是稍偏下，具体缘由见下回分解）
* 图片也是属于文本，当文本字体是14px时，通过line-height看起来图片稍稍偏下，当字体调到很大时，偏差就会更明显

## 行内框盒子模型：
1. 内容区域
![](http://qiniu.sponges.cn/201802232209_329.png?imageView2/0/w/680/h/480)
2. 内联盒子
![](http://qiniu.sponges.cn/201802232210_310.png?imageView2/0/w/680/h/480)
3. 行框盒子
![](http://qiniu.sponges.cn/201802232211_792.png?imageView2/0/w/680/h/480)
4. 包含盒子
![](http://qiniu.sponges.cn/201802232211_124.png?imageView2/0/w/680/h/480)
> 其中4包含3,3包含2，2与1关系说不清

## line-height与内联元素的高度机理
> 内联元素高度由行高决定

![](http://qiniu.sponges.cn/201802232216_101.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232217_350.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232219_513.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232219_124.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232219_829.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232222_940.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232224_297.png?imageView2/0/w/680/h/480)
> 行高 不等于 他内联元素中那个最高的元素, 多行文本的高度就是单行文本的高度累加

![](http://qiniu.sponges.cn/201802232226_44.png?imageView2/0/w/680/h/480)

##  line-height各类属性值
![](http://qiniu.sponges.cn/201802232229_618.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232230_245.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232231_637.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232232_90.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232235_360.png?imageView2/0/w/680/h/480)
> 推荐使用第一种

![](http://qiniu.sponges.cn/201802232238_444.png?imageView2/0/w/680/h/480)

## line-height与图片的表现
![](http://qiniu.sponges.cn/201802232244_64.png?imageView2/0/w/680/h/480)

## line-height的实际应用
![](http://qiniu.sponges.cn/201802232247_47.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232248_755.png?imageView2/0/w/680/h/480)
* 可能还需加上：max-width:100%