## transition渐变
```
/* 过渡的属性详解*/
/* 如果希望所有的属性都发生过渡 使用过all*/
transition-property: all;
/* 过渡持续时间*/
transition-duration:4s;
/* 运动曲线*/
/* linear 线性 ease ease-in ease-out ease-in-out :先加速后减速 */
transition-timing-function: ease-in-out;
/* 过渡延迟*/
transition-delay: 1s;
/*transition:width 2s,background-color 2s;*/
/* 过渡必须加给盒子本身*/
/* 如果多个过度的 特性是一样的 可以简写*/
/* transition: 过渡属性 持续时间 运动曲线 延迟时间*/
transition:all 4s linear 1s ;
```

## 原点 transform-origin
任何一个元素都有一个中心点，默认情况之下，其中心点是居于元素X轴和Y轴的50%处。如下图所示：
![](http://qiniu.sponges.cn/201803081405_22.png?imageView2/0/w/880/h/680)

transform-origin取值和元素设置背景中的background-position取值类似
![](http://qiniu.sponges.cn/201803081407_55.png?imageView2/0/w/880/h/680)
改变  transform-origin 就可以改变变形中心点
```
.wrapper div {
  background: orange;
  -webkit-transform: rotate(45deg);
  transform: rotate(45deg);
}
.transform-origin div {
  -webkit-transform-origin: left top;
  transform-origin: left top;
}
```
![](http://qiniu.sponges.cn/201803081410_77.png?imageView2/0/w/880/h/680)


## 2d变换
```
1. scale放缩 根据中心原点对对象进行缩放。
scale(水平放缩比例，垂直放缩比例)；
大于1：放大
小于1：缩小
如果只写一个值等比例缩放
transform: scale(2,0.5);

2. translate:\(水平位移，垂直位移\)；
正值：向右向下
负值：向左向上
如果只写一个值 水平移动
百分比 ：相对于自身移动
transform:translate(-50%,-50%);
结合 position: absolute;
left:50%;
top:50%;
可做水平垂直居中

3. rotate旋转
rotate（角度） 旋转 相对原点中心
正值：顺时针
负值：逆时针
transform:rotate(-945deg);
```

## 矩阵
matrix(scaleX(),skewX(),skewY(),scaleY(),translateX(),translateY());

## 3d变换
```
1. 透视

电脑显示屏是一个2D平面，图像之所以具有立体感（3D效果），其实只是一种视觉呈现 ，通过透视可以实现此目的。 perspective
通过透视产生的3D效果，只是视觉呈现而已，并不是真正的3d立体的盒子；

2. 添加透视 ，添加透视会有视觉上的3d效果 ，设置的是 用户的眼睛 和 屏幕的距离, 这个属性设置给 父盒子的，子盒子3d效果

父元素 perspective:300px; 视觉距离
transform-style:preserve-3d; 可以让子盒子保证3D效果， 指定子元素定位在三维空间内

子元素 rotateX 绕水平方向旋转
rotateY 绕垂直方向旋转
rotateZ 平行于屏幕方向旋转

transform:translateX(500px); 沿着X轴移动
transform:translateY(500px); 沿着Y轴移动
transform:translateZ(500px); 沿着Z轴移动 必须添加透视 才能看到效果
```
参考 https://codepen.io/crazyzhanyue/pen/QmLBzg

## 动画的使用：
1. 先定义一个动画

```
  @keyframes 动画名称{
    from{
    动画初始状态
    }
    to{
    动画结束状态
    }
  }
```

2. 调用动画

```
  animation: KeyframesName duration  iteration-count timing-function delay play-state direction fill-mode;
  animation: 动画名称 动画时间 执行次数 运动曲线 延迟执行 结束后状态 是否反向；

  运动曲线:
  linear  匀速（等于 cubic-bezier(0,0,1,1)）。
  ease  先慢，后快，然后慢速结束（cubic-bezier(0.25,0.1,0.25,1)）。
  ease-in 慢开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)）。
  ease-out  以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）。
  ease-in-out 以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）。
  cubic-bezier(n,n,n,n) 在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值。

  执行次数
  animation-iteration-count: infinite | <number>
  inifnite: 无限次执行

  动画播放方向
  animation-direction:normal | alternate
  animation-direction 值是 "alternate"，则动画会在奇数次数（1、3、5 等等）正常播放，而在偶数次数（2、4、6 等等）向后播放。

  结束后状态
  animation-fill-mode: none | forwards | backwards | both;
  none ： 不改变默认行为
  forwards ： 当动画完成后，保持最后一个属性值（在最后一个关键帧中定义）
  backwards ： 在 animation-delay 所指定的一段时间内，在动画显示之前，应用开始属性值（在第一个关键帧中定义）
  both ： 向前和向后填充模式都被应用

  播放状态:
  animation-play-state:running | paused;
  running是其默认值,paused停止动画


  alternate: 反向执行
  steps\(5\): 让动画分步执行；

  animation: gun 2s 3 linear;

```

3. 帧动画

```
.box{
      width: 5px;
      height: 200px;
      margin:50px auto;
      background-color: \#000;
      border-radius:50% 50% 0 0 / 50% 50% 0 0 ;
      transform-origin: center bottom;
      animation: rot 60s steps\(60\); //60s执行完毕 steps 60次执行
    }
    @keyframes rot {
        0%{
        }
        100%{
            transform:rotate\(360deg\);
        }
}
```

## 总结

CSS3中的三种动画:tranform形变动画/transition缓动动画/animation逐帧动画;

tranform: rotate旋转/skew扭曲/scale缩放/translate移动/matrix矩阵变形;

transition: property duration timing-function delay;

animation: KeyframesName duration timing-function delay iteration-count direction play-state fill-mode;

