## vertical-align 支持的四种类型(支持inherit 继承)
![](http://qiniu.sponges.cn/201802241336_282.png?imageView2/0/w/680/h/480)
 - 数值百分比类
![](http://qiniu.sponges.cn/201802241342_591.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802241344_950.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802241344_268.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802241346_181.png?imageView2/0/w/680/h/480)

## vertical-align起作用的前提
> vertical-align应用于inline水平和table-cell元素

![](http://qiniu.sponges.cn/201802241356_259.png?imageView2/0/w/680/h/480)
- block不生效
![](http://qiniu.sponges.cn/201802241357_138.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802241359_607.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802241359_557.png?imageView2/0/w/680/h/480)
- 间接改变元素属性，vertical-align也会失效，如float，absoulate
![](http://qiniu.sponges.cn/201802241403_357.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802241403_807.png?imageView2/0/w/680/h/480)

- table-cell(作用于自身)元素
![](http://qiniu.sponges.cn/201802241406_993.png?imageView2/0/w/680/h/480)

## vertical-align与line-height
![](http://qiniu.sponges.cn/201802241413_172.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802241420_483.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802241513_494.png?imageView2/0/w/680/h/480)

## vertical-align垂直居中
![](http://qiniu.sponges.cn/201802241404_299.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802241526_746.png?imageView2/0/w/680/h/480)

## text-top和text-bottom
与父元素字体大小有关，不受行高以及其他内联元素影响
![](http://qiniu.sponges.cn/201802241533_485.png?imageView2/0/w/680/h/480)

## vertical-align上标下标类
1. html中的上标:`<sup>`类似于vertical-align:supper
2. html中的下标:`<sub>`类似于vertical-align:sub

> v-a前后元素不会直接影响，但是会通过改变父级影响前后元素

## vertical-align的实际应用
1. 小图标文字对齐,兼容性比较好
![](http://qiniu.sponges.cn/201802241554_141.png?imageView2/0/w/680/h/480)
2. 个数不定的文字内容和不定尺寸图片垂直居中对齐
![](http://qiniu.sponges.cn/201802241409_577.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802241411_125.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802241558_399.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802241559_287.png?imageView2/0/w/680/h/480)
> display:inline-block;具有收缩特性，由于这里i标签什么内容都没有，所以天然的宽度为0