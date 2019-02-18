##relative对absolute的限制作用：
1. 限制left/top/right/bottom定位：
父元素使用了relative定位后，使用了absolute的子元素无法越过父元素进行定位；
2. 限制z-index层级：
使用了relative定位的同级元素，其本身的z-index值将决定其子元素的z-index层级；
3. 限制在overflow下的嚣张气焰：
子元素设置了absolute定位时，其父级元素的 overflow 属性无法对该子元素进行有效约束。但父级元素再设置relative定位时，会把该子元素的超出部分砍掉。

##relative对fixed的限制作用：
1. 限制z-index层级： 与对absolute限制z-index的作用一样。

##relative自身的定位特性：
1. 相对自身：即相对于原来自身的位置进行偏移；
2. 无入侵：即不影响原来的文档流。（应用：实现自定义拖拽）

##relative元素设置了对立属性：top/bottom 或 left/right 时：
结论：
1. 绝对定位是拉伸；
2. 相对定位是斗争。
top会使bottom无效，声明left后则会导致right无效。

##relative与z-index层级：
1. 提高元素的层叠上下文：鬼畜级别，即相当有效。
2. 新建层叠上下文与层级控制：
当元素的z-index为一个具体的数值（包括0）时，设置了relative后会使元素新建层叠上下文，即元素的子元素层级会被该元素所约束。
在IE6/7以外的浏览器中，当元素的z-index为auto时，即使设置了relative，元素也无法约束其子元素的层级（即子元素会参考更上级元素的层叠上下文进行层叠排序）。

##relative的最小化影响原则：即尽量降低relative属性对其他元素或布局的潜在影响
1. 尽量避免使用relative，子元素直接使用absolute，而父级元素不必要使用relative就可使子元素相对于父级元素进行定位（只要子元素不使用left、top等属性即可，可使用margin-left、margin-top代替）
2. 若子元素有很多同级的元素，应当将子元素拿出来与父级元素同级后，再为其套一父元素，对该新父元素使用relative来实现子元素如右对齐的定位。可避免其原来的同级元素的层级关系被破坏

