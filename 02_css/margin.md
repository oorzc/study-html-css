## margin与可视尺寸
![](http://qiniu.sponges.cn/201802112151_367.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112152_677.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112154_646.png?imageView2/0/w/680/h/480)

滚动容器上下留白，非Chrom浏览器底部不留白（padding上下边距设置无效）此时应使用margin
![](http://qiniu.sponges.cn/201802112156_772.png?imageView2/0/w/680/h/480)


## margin与百分比单位
![](http://qiniu.sponges.cn/201802112158_167.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112200_105.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112203_629.png?imageView2/0/w/680/h/480)

margin 重叠 宽高 2:1
![](http://qiniu.sponges.cn/201802112206_87.png?imageView2/0/w/680/h/480)

## margin 重叠
![](http://qiniu.sponges.cn/201802112210_765.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112211_276.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112213_773.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112220_15.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112220_148.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112221_712.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112223_218.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112225_721.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112227_301.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112227_945.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112228_241.png?imageView2/0/w/680/h/480)

## margin重叠的计算规则
![](http://qiniu.sponges.cn/201802112229_765.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112230_189.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112231_487.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112232_618.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112236_840.png?imageView2/0/w/680/h/480)

## 善用margin重叠
![](http://qiniu.sponges.cn/201802112237_449.png?imageView2/0/w/680/h/480)

## margin:auto
![](http://qiniu.sponges.cn/201802112241_934.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112244_952.png?imageView2/0/w/680/h/480)
* 高度无法自动填充

![](http://qiniu.sponges.cn/201802112247_524.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112249_905.png?imageView2/0/w/680/h/480)

## margin 负值定位
* 两端对齐
![](http://qiniu.sponges.cn/201802112251_570.png?imageView2/0/w/680/h/480)
* 等高布局
![](http://qiniu.sponges.cn/201802112255_108.png?imageView2/0/w/680/h/480)
* 右侧固定
![](http://qiniu.sponges.cn/201802112259_843.png?imageView2/0/w/680/h/480)

## margin失效
```
1. inline水平元素的垂直margin无效。2个前提：
（1）非替换元素，例如，不是<img>元素。
（2)正常书写模式：`<span style="margin-right:220px;">设置margin</span>`
2. margin重叠。
3. display:table-cell与margin：
display:table-cell/ display:table-row等声明的margin无效。
（1）可以通过display:table-cell实现两栏布局，但是无法通过table-cell添加margin撑开间距。
（2）firefox：返回table-cell，实质是inline-block，margin不会重叠。
ie：返回table-cell，实质是table-cell，margin会重叠。
4. position:absolute与margin
（1）绝对定位元素非定位方位的margin值“无效”。
（2）对定位没有影响，但是对占据空间有影响。绝对定位的margin值一直有效，只是不像普通元素那样，可以对兄弟元素产生影响。
5. 鞭长莫及导致的margin无效。
（1）浮动和绝对定位是破坏性属性，会破坏整个页面元素的布局。（第11分钟）
6. 内联特性导致的margin无效。
内联元素默认基线对齐。
图片受文字的影响，文字不能在div外面，图片为了和文字对齐，在与文字的基线对齐后，margin-top:-300，值的绝对值再往上升的时候，margin也不会对图片起作用。
![](http://qiniu.sponges.cn/201802112310_590.png?imageView2/0/w/680/h/480)
```

## margin-start
```
1. 正常的流向，margin-start等同于margin-left，两者重叠不累加。
2. 如果水平流是从右往左，margin-start等同于margin-right。
3. 在垂直流下（writing-mode:verticall-*;）,margin-start等同于margin-top。
+ margin-start、 border-start，随着流特性应运而生。
+ webkit下的其他margin特性。
 - margin-before：默认流向的情况下，等同于margin-top。
 - margin-after：默认流向的情况下，等同于margin-bottom。
+ margin-collapse：
 - -webkit-margin-collapse: <collapse>（默认-重叠） | <discard>（取消） | <separate>（分隔）
 ```
