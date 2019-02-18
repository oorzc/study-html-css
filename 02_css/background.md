   # 背景
   ## 背景尺寸
   ```
            /* 控制背景的大小*/
            /*具体数值*/
            background-size: 500px 500px;
            /* 百分比*/
            background-size:50% 50%;

            /* cover  覆盖   contain: 包含*/
            /* cover 会保证完全覆盖盒子，但不能保证完整显示*/
            background-size:cover;

            /*contain :包含*/
            /* 保证背景图片最大化的在盒子中等比例显示，但不保证能铺满盒子*/
            background-size: contain;
```

## 背景原点
```
            /* 背景原点  控制背景从什么地方开始显示*/
            /*(默认值)*/
            background-origin: padding-box;
            /*从border-box开始显示*/
            background-origin: border-box;
            /*从content-box开始显示*/
            background-origin: content-box;
```
![](http://qiniu.sponges.cn/201803081143_518.png?imageView2/0/w/880/h/680)

## 背景裁剪
```
            border-box :从 border-box开始裁剪
            padding-box :从 padding-box开始裁剪
            content-box :从 content-box开始裁剪
            background-clip:content-box;
```
![](http://qiniu.sponges.cn/201803081144_927.png?imageView2/0/w/880/h/680)

## 背景固定
background-attachment: scroll(随着内容一起滚动) | fixed (不滚动)

## 多背景
```
         /* 给盒子加多个背景，按照背景语法格式书写，多个背景使用逗号隔开 */
        .demo{
            width: 300px;
            height: 140px;
            border: 1px solid #999;
            background-image: url(http://img.mukewang.com/54cf2365000140e600740095.jpg),
                              url(http://img.mukewang.com/54cf238a0001728d00740095.jpg),
                              url(http://img.mukewang.com/54cf23b60001fd9700740096.jpg);
            //分别设置每张图背景位置 ，重复方式
            background-position: left top, 100px 0, 200px 0;
            background-repeat: no-repeat, no-repeat, no-repeat;
            margin:0 0 20px 0;
        }
        .task {
            width: 300px;
            height: 140px;
            border: 1px solid #999;
            background:url(http://static.mukewang.com/static/img/logo_index.png) no-repeat,
                       url(http://static.mukewang.com/static/img/logo_index.png) no-repeat;
            //分别设置每张图背景位置 ，背景大小，重复方式
            background-position:0 0,100% 100%;
            background-size:200px 60px,100px 50px;
            background-repeat:no-repeat,no-repeat;
            //合成写法
            background:url(http://static.mukewang.com/static/img/logo_index.png) no-repeat left top /75% 55%,
             url(http://static.mukewang.com/static/img/logo_index.png) no-repeat right bottom /50% 40% ;
        }
```
![](http://qiniu.sponges.cn/201803081158_302.png?imageView2/0/w/880/h/680)

## 背景动画
![](http://qiniu.sponges.cn/201803071516_653.png?imageView2/0/w/880/h/680)
```
        .container{
            width: 100px;
            height: 100px;
            border: 1px solid red;
            background: url(./animal.png) no-repeat;
            animation: run 1s infinite;
            animation-timing-function: steps(1);
        }
        @keyframes run{
            0%{
                background-position: 0 0;
            }
            12.5%{
                background-position: -100px 0;
            }
            25%{
                background-position: -200px 0;
            }
            37.5%{
                background-position: -300px 0;
            }
            50%{
                background-position: 0 -100px;
            }
            62.5%{
                background-position: -100px -100px;
            }
            75%{
                background-position: -200px -100px;
            }
            87.5%{
                background-position: -300px -100px;
            }
            100%{
                background-position: 0 0;
            }
        }
```

## 背景渐变
![](http://qiniu.sponges.cn/201803081115_874.png?imageView2/0/w/880/h/680)
![](http://qiniu.sponges.cn/201803081115_330.png?imageView2/0/w/880/h/680)
```
     语法：
            linear-gradient(方向，起始颜色，终止颜色);
            方向：to left   to right  to top   to bottom 　角度　30deg
            起始颜色
            终止颜色
            1. background-image: linear-gradient(to right,yellow ,green);
            2. background-image: linear-gradient(to right,
                yellow 0% ,
                red 40% ,
                green 70% ,
                blue 100%
                );
            3. background-image: linear-gradient(
                135deg,
                #000 0%,
                #000 25%,
                #fff 25%,
                #fff 50%,
                #000 50%,
                #000 75%,
                #fff 75%,
                #fff 100%
                );
```
实例：

background-image:linear-gradient(to left, red, orange,yellow,green,blue,indigo,violet);

![](http://qiniu.sponges.cn/201803081117_529.png?imageView2/0/w/880/h/680)

参考: https://codepen.io/crazyzhanyue/pen/KQORxY

## 径向渐变
```
        /*
            radial-gradient（辐射半径, 中心的位置，起始颜色，终止颜色）;
            中心点位置：at  left  right  center bottom  top
        */
        div:nth-child(1){
            background-image: radial-gradient(at left top,yellow,green);
        }
        div:nth-child(2){
            background-image: radial-gradient(at 50px 50px,yellow,green);
        }
        div:nth-child(3){
            background-image: radial-gradient(100px at center,yellow ,green);
        }
        div:nth-child(4){
            background-image: radial-gradient(100px at center,
            yellow 0% ,
            green 30%,
            blue 60%,
            red 100%);
        }
        div:nth-child(5){
            background-image: radial-gradient(100px 50px  at center,yellow ,green);
        }
```

参考: https://codepen.io/crazyzhanyue/pen/VQoxqz

