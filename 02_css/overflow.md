## overflow
1. 当overflow-x 与 overflow-y值相同时 ，等同于overflow
2. 当overflow-x 与 overflow-y值不相同时，且其中一个值为visible,另一个被赋予，hidden,auto,scroll那这个visvible会被重置为auto;
![](http://qiniu.sponges.cn/201802231909_486.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802231910_421.png?imageView2/0/w/680/h/480)

## overflow: 作用前提
1. 非 display: inline 水平
2. 对应方位的尺寸限制: width/height/max-width/max-height/absolute 拉伸
3. 对于单元格 td 等, 需要 table 为 table-layout: fixed 状态才可以
![](http://qiniu.sponges.cn/201802231911_496.png?imageView2/0/w/680/h/480)

## 滚动条出现条件
![](http://qiniu.sponges.cn/201802231919_910.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802231925_850.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802231929_632.png?imageView2/0/w/680/h/480)

## 滚动高度
```js
	var st = document.documentElement.scrollTop || document.body.scrollTop
```
![](http://qiniu.sponges.cn/201802231930_796.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802231937_483.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232055_569.png?imageView2/0/w/680/h/480)

## 自定义滚动条
![](http://qiniu.sponges.cn/201802232056_5.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232057_104.png?imageView2/0/w/680/h/480)
原生滚动回调 ：-webkit-overflow-scrolling: touch

## BFC与overflow
![](http://qiniu.sponges.cn/201802232113_996.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232109_771.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232114_56.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232112_710.png?imageView2/0/w/680/h/480)

## overflow 失效
![](http://qiniu.sponges.cn/201802232117_801.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232126_519.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232127_618.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232128_640.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232129_667.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232129_530.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232130_73.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232133_264.png?imageView2/0/w/680/h/480)

## 依赖overflow 的样式表现
![](http://qiniu.sponges.cn/201802232135_624.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232136_600.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232137_841.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232138_912.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232139_724.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802232147_137.png?imageView2/0/w/680/h/480)
> 不足之处：锚点定位的穿透性很强，会定位到滚动条最上面的位置，oveflow和锚点技术适合应用在单页应用（页面只有一屏，无滚动）上。