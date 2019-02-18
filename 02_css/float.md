## float的设计初衷： 仅仅是为了实现文字环绕效果
### float的感性认知：
包裹性：
1. 收缩：元素应用了float后，宽度收缩，紧紧地包裹住内容（即元素的宽度收缩到元素内的内容的宽度大小）
2. 坚挺：原来没有高度，但元素应用了float后，元素的高度突然扩展到内容的高度大小
3. 隔绝：元素应用了float后，盒子里面的内容发生了任何事情，都与盒子外的内容无关（BFC）
破坏性：
1. 子元素应用了float后，父容器塌陷：父容器的高度变为0

### 具有包裹性（BFC特性）的其他属性：
1. display: inline-block/table-cell
2. position: absolute/fixed/sticky
3. overflow: hidden/scroll

### 具有破坏性的其他属性：
1. display: none
2. position: absolute/fixed/sticky

### 清除浮动：
```css
.clearfix:after{
    content: '';
    display: table;
    clear: both;
 }
 .clearfix{ *zoom: 1; }
```
切记，.clearfix 只需应用在浮动元素的父级元素上 浮动的特性：
1. 元素block块状化（砖头化）
2. 破坏性造成的紧密排列特性（去空格化）
