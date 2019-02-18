## css选择器

1. css2选择器：

   ```
   .box 类名选择器
   #box　id选择器
   div p 后代选择器
   div.box 交集选择器
   div,p,span 并集选择器
   div>p 子代
   * : 通配符
   div+p: 选中div后面相邻的第一个p
   div~p: 选中的div后面所有的p
   div>p: 子代
   div+p： div后面相邻的第一个p
   div~p: div后面所有的兄弟p
   ```

2. 属性选择器：

   ```
   id选择器    #     通过id 来选择
   类名选择器  .     通过类名来选择
   属性选择器  []    通过标签属性来选择器

   语法：
   标志性符号：[]
   ^: 开头  $:结尾  *：包含
   E[title]  : 选中页面的E元素，并且E需要带有title属性
   E[title="abc"] :选中页面的E元素，并且E需要带有title属性,属性值为abc
   E[title^="abc"] :选中页面的E元素，并且E需要带有title属性,属性值以abc开头
   E[title$="abc"] :选中页面的E元素，并且E需要带有title属性,属性值以abc结尾
   E[title*="abc"] :选中页面的E元素，并且E需要带有title属性,属性值包含abc
   ```

1. 结构伪类选择器：

   ```
   E：first-child　选中父元素中的第一个子元素
   E：last-child　选中父元素中的最后一个子元素
   E：nth-child(1)　选中父元素中的第5个子元素
       n: 0,1,2,3,4。。。
       偶数： 2n  even
       奇数：2n-1 odd
       前5个： -n+5
   E：nth-last-child(3): 从后向前选择， 选中倒数第3个
    div:nth-child(9)
    注意：所选到的元素的类型 必须是指定的类型E,否则选择无效；

   E：empty 表示元素为空的状态
   E:target: 表示元素被激活的状态  要配合锚点使用
   ```

2. 伪元素：

   ```
   通过css模拟出html效果
   E::before
   E::after  必须有content 属性
   ```

3. 伪元素选择器：

   ```
   E::first-letter　选中第一个字母
   E::first-line选中第一行
   E::selection: 表示选择的区域 通过设置 color  background
   ```



