## z-index:auto /整数值/ inherit
1. z-index支持的特性:支持负值;
2. 支持css3 animation动画;
3. 在css2.1时代，需要和定位元素配合使用
4. 如果不考虑CSS3,只有定位元素(position:relative/absolute/fixed/sticky)的z-index才有作用 在CSS3中有例外

## 层叠上下文
![](http://qiniu.sponges.cn/201802231553_230.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802222154_474.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802222158_635.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802222159_181.png?imageView2/0/w/680/h/480)
>  z-index：auto不会创建层叠上下文，z-index：0会创建层叠上下文

![](http://qiniu.sponges.cn/201802231759_645.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802231800_149.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802231806_787.png?imageView2/0/w/680/h/480)

* 淡入淡出效果
![](http://qiniu.sponges.cn/201802231813_776.png?imageView2/0/w/680/h/480)
> 图片在文字的后面，最开始的opacity值小于1，产生了一个层叠上下文，这俩都是内容，根据后来居上的原则，图片会覆盖文字，当opacity值等于1的时候，动画结束，文字才重新显示出来，这个时候position:absolute的元素z-index为auto,层叠顺序高于img等inline元素，文字重见天日

## z-index的相关实践
1. 最小化影响原则：
![](http://qiniu.sponges.cn/201802231856_612.png?imageView2/0/w/680/h/480)
2. 不范二准则：
![](http://qiniu.sponges.cn/201802231856_694.png?imageView2/0/w/680/h/480)
3. 组件层级计数器：
> 如何解决浮层组件因z-index被覆盖的问题？使用组件层级计数器的方法，找到body中最大的z-index，然后将自己的组件的z-index值设置为最大值加一，就可以解决。

![](http://qiniu.sponges.cn/201802231857_842.png?imageView2/0/w/680/h/480)
4. 负值z-index与可访问性隐藏
可访问性隐藏：人肉宴不可见，但是辅助设备可以识别。
z-index负值元素在层叠上下文的背景之上，其他元素之下

![](http://qiniu.sponges.cn/201802231855_489.png?imageView2/0/w/680/h/480)