## absolute与float的兄弟关系：
 * 都具有包裹性（父元素应用绝对定位后，父元素的宽度会收缩，但保持包裹住子元素的状态）
 * 都具有破坏性（子元素应用绝对定位后，父元素的高度会塌陷）

## absolute与relative：
* 当子元素只是浮动到父元素的左上角（left:0; top:0;）处时，父元素不必设置 position: relative; ，子元素直接设置 position: absolute; 就可以了

## 无依赖的absolute定位`跟随性`：
![](http://qiniu.sponges.cn/201802101723_731.png?imageView2/0/w/880/h/680)
* 不受relative限制的absolute定位，行为表现上`前提是不使用top/right/bottom/left任何一个属性或使用auto作为值（即只是悬浮在原来位置的z轴的上方）`
* `位置跟随 原来什么位置，绝对定位后还是在那个位置（但不包括float的情况，绝对定位会去浮动）`
如果元素是block水平的，当应用了absolute绝对定位后，依然是换行显示的。（即前面的文字不会被挡住。IE8+支持，IE7的修复办法：在绝对定位外面套一层空div即可） 如果元素是inline/inline-block水平的，当应用了absolute绝对定位后，依然保持在前面文字的后面 （另外，在Chrome浏览器下，当元素设置了absolute定位后，再改变元素的display属性为inline/block时，页面不会重新渲染）

![](http://qiniu.sponges.cn/201802101610_315.png?imageView2/0/w/880/h/680)
```css
.scroll {
    width: 500px; height: 300px;
	margin: 200px auto 0;
	margin-top: -webkit-calc(50vh - 150px);
	margin-top: calc(50vh - 150px);
	border: 1px solid #ccc;
	border-radius: 3px;
	box-shadow: 0 0 3px rgba(0,0,0,.35);
	background-color: #fff;
	overflow: auto;
}
.close {
    position: absolute;
	width: 34px; height: 34px;
	margin: -17px 0 0 487px;
	background: url(http://img.mukewang.com/5444835b000100ce00340075.png) no-repeat;
}
.close:hover {
    background-position: 0 -41px;
}
img {
	display: block;
	margin: 10px;
}
```

```html
<div class="scroll">
	<a href="javascript:" class="close" title="关闭"></a>
	<img src="http://img.mukewang.com/54447b06000171a002560191.jpg">
    	<img src="http://img.mukewang.com/54447f550001ccb002560191.jpg">
</div>
```




## 图标定位（无依赖绝对定位）
![](http://qiniu.sponges.cn/201802101648_357.png?imageView2/0/w/880/h/680)
```css
.icon-hot { position: absolute; width: 28px; height: 11px; margin: -6px 0 0 2px; background: url(http://img.mukewang.com/545304730001307300280011.gif); }
.icon-recom { position: absolute; line-height: 20px; padding: 0 5px; background-color: #f60; color: #fff; font-size: 12px; }
.icon-vip { position: absolute; width: 36px; height: 36px; margin-left: -36px; background: url(http://img.mukewang.com/5453048000015d8800360036.gif); text-indent: -9em; overflow: hidden; }
```

```html
  <div class="nav">
            <h3 class="nav-list">
            	<a href="http://www.imooc.com/course/list" class="nav-a">课程</a>
            </h3>
            <h3 class="nav-list">
            	<a href="http://www.imooc.com/wenda" class="nav-a">问答</a>
            </h3>
            <h3 class="nav-list">
            	<a href="http://www.imooc.com/seek/index" class="nav-a">
                	求课<i class="icon-hot"></i>
                </a>
            </h3>
  </div>
<div class="course">
    <a href="http://www.imooc.com/view/121" class="course-list">
        <div class="course-list-img">
        	<span class="icon-recom">推荐</span>
            <img width="280" height="160" alt="分享：CSS深入理解之float浮动" src="http://img.mukewang.com/53d74f960001ae9d06000338-300-170.jpg"><!--
            --><i class="icon-vip">vip</i>

          此处的注释<！- -  -->是为了使vip与img完美贴合，删除他俩之间的空隙

        </div>
        <h5 class="course-list-h">分享：CSS深入理解之float浮动</h5>
        <div class="course-list-tips">
            <span class="l">已完结</span>
            <span class="r">3514人学习</span>
        </div>
    </a>
</div>
  ```

## 下拉框定位
![](http://qiniu.sponges.cn/201802101705_483.png?imageView2/0/w/880/h/680)

`<ul>在<input>前，设置<ul>定位absolute定位，<input>坍缩到<ul>的位置。再用margring定位。`

```css
.course-search-input { width: 200px; line-height: 18px; padding: 10px; margin: 0; border: 0 none; font-size: 12px; font-family: inherit; float: left; }
.course-sidebar-result { display: none; position: absolute; width: 260px; margin: 39px 0 0 -1px; padding-left: 0; list-style-type: none; border: 1px solid #e6e8e9; background-color: #fff; box-shadow: 0px 1px 2px #d5d7d8; font-size: 12px; }
```
```html
        <div class="course-sidebar-search">
        	<ul id="result" class="course-sidebar-result">
            	<li><a href="http://www.imooc.com/view/121">分享：CSS深入理解之float浮动</a></li>
                <li><a href="http://www.imooc.com/view/118">案例：CSS圆角进化论</a></li>
                <li><a href="http://www.imooc.com/view/93">案例：CSS Sprite雪碧图应用</a></li>
                <li><a href="http://www.imooc.com/view/77">案例：CSS3 3D 特效</a></li>
                <li><a href="http://www.imooc.com/view/57">案例：如何用CSS进行网页布局</a></li>
            </ul>
        	<input class="course-search-input" placeholder="课程搜索">
            <a href="javascript:" class="course-search-btn">搜索</a>
      </div>
 ```

https://www.imooc.com/code/4541

## 登陆注册
* `*`实现
![](http://qiniu.sponges.cn/201802101726_764.png?imageView2/0/w/680/h/480)
* 文字溢出
![](http://qiniu.sponges.cn/201802101729_538.png?imageView2/0/w/680/h/480)
* 图标对齐
![](http://qiniu.sponges.cn/201802101730_385.png?imageView2/0/w/680/h/480)

## 脱离文档流 层级
![](http://qiniu.sponges.cn/201802101736_55.png?imageView2/0/w/680/h/480)

## 全屏效果（拉伸效果）
![](http://qiniu.sponges.cn/201802101741_440.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802101741_564.png?imageView2/0/w/680/h/480)
```html
<title>没有宽度和高度声明实现的全屏自适应效果</title>
<style>
html, body { height: 100%; }
.overlay {
    position: absolute;
    left: 0; top: 0; right: 0; bottom: 0;
    background-color: #000;
    opacity: .5; filter: alpha(opacity=50);
}
</style>
<div class="overlay"></div>
```

![](http://qiniu.sponges.cn/201802112108_626.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112110_525.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112110_279.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112105_912.png?imageView2/0/w/680/h/480)

* 优先级上 width/height设置的尺寸 大于 拉伸而来的尺寸
![](http://qiniu.sponges.cn/201802112103_407.png?imageView2/0/w/680/h/480)

* 高度自适应九宫格
```html
<style>
html, body { height: 100%; margin: 0; }
.page {
    position: absolute;
    left: 0; top: 0; right: 0; bottom: 0;
}
.list {
    float: left;
    height: 33.3%; width: 33.3%;
    position: relative;
}
.list:before {
    content: '';
    position: absolute;
    left: 10px; right: 10px; top: 10px; bottom: 10px;
    border-radius: 10px;
    background-color: #cad5eb;
}
.list:after {
    content:attr(data-index);
    position: absolute;
    height: 30px;
    left: 0; right: 0; top: 0; bottom: 0;
    margin: auto;
    text-align: center;
    font: 24px/30px bold 'microsoft yahei';
}
</style>
<body>
<div class="page">
    <div class="list" data-index="1"></div>
    <div class="list" data-index="2"></div>
    <div class="list" data-index="3"></div>
    <div class="list" data-index="4"></div>
    <div class="list" data-index="5"></div>
    <div class="list" data-index="6"></div>
    <div class="list" data-index="7"></div>
    <div class="list" data-index="8"></div>
    <div class="list" data-index="9"></div>
</div>
</body>
```
![](http://qiniu.sponges.cn/201802112121_138.png?imageView2/0/w/680/h/480)

## absolute与整体布局
![](http://qiniu.sponges.cn/201802112125_491.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112126_530.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112127_835.png?imageView2/0/w/680/h/480)、
![](http://qiniu.sponges.cn/201802112128_954.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112129_713.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112131_603.png?imageView2/0/w/680/h/480)
![](http://qiniu.sponges.cn/201802112132_418.png?imageView2/0/w/680/h/480)

demo https://www.imooc.com/code/5071

![](http://qiniu.sponges.cn/201802112142_870.png?imageView2/0/w/680/h/480)
```html
<style type="text/css">
    html,
    body {
      margin: 0;
      height: 100%;
    }

    .overlay,
    .page {
      position: absolute;
      left: 0;
      top: 0;
      right: 0;
      bottom: 0;
    }

    .header,
    .aside,
    .content,
    .footer {
      position: absolute;
    }

    .header,
    .content,
    .footer {
      left: 0;
      right: 0;
    }

    button {
      width: 100%;
      height: 100%;
      background-color: transparent;
      border-width: 0;
      outline: none;
    }

    .loader {
      width: 1em;
      height: 1em;
      margin: 0 auto;
      font-size: 50px;
      text-indent: -9999em;
      -webkit-animation: load 1.5s infinite ease;
      animation: load 1.5s infinite ease;
      border-radius: 50%;
      overflow: hidden;
    }

    @keyframes load {
      0% {
        -webkit-transform: rotate(0deg);
        transform: rotate(0deg);
        box-shadow: -0.11em -0.83em 0 -0.4em #ffffff, -0.11em -0.83em 0 -0.42em #ffffff, -0.11em -0.83em 0 -0.44em #ffffff, -0.11em -0.83em 0 -0.46em #ffffff, -0.11em -0.83em 0 -0.477em #ffffff;
      }
      5%,
      95% {
        box-shadow: -0.11em -0.83em 0 -0.4em #ffffff, -0.11em -0.83em 0 -0.42em #ffffff, -0.11em -0.83em 0 -0.44em #ffffff, -0.11em -0.83em 0 -0.46em #ffffff, -0.11em -0.83em 0 -0.477em #ffffff;
      }
      30% {
        box-shadow: -0.11em -0.83em 0 -0.4em #ffffff, -0.51em -0.66em 0 -0.42em #ffffff, -0.75em -0.36em 0 -0.44em #ffffff, -0.83em -0.03em 0 -0.46em #ffffff, -0.81em 0.21em 0 -0.477em #ffffff;
      }
      55% {
        box-shadow: -0.11em -0.83em 0 -0.4em #ffffff, -0.29em -0.78em 0 -0.42em #ffffff, -0.43em -0.72em 0 -0.44em #ffffff, -0.52em -0.65em 0 -0.46em #ffffff, -0.57em -0.61em 0 -0.477em #ffffff;
      }
      100% {
        -webkit-transform: rotate(360deg);
        transform: rotate(360deg);
        box-shadow: -0.11em -0.83em 0 -0.4em #ffffff, -0.11em -0.83em 0 -0.42em #ffffff, -0.11em -0.83em 0 -0.44em #ffffff, -0.11em -0.83em 0 -0.46em #ffffff, -0.11em -0.83em 0 -0.477em #ffffff;
      }
    }

    .overlay-theme {
      background-color: rgba(0, 0, 0, .5);
      z-index: 9;
    }

    .header {
      top: 0;
      height: 50px;
      min-height: 50px;
      background-color: royalblue;
    }

    .aside {
      /* 宽度 24% 只是根据黄金分割算出来的一个数字，100 * 61.8% * 61.8% = 23.6% */
      width: 24%;
      top: 50px;
      bottom: 50px;
      background-color: lightseagreen;
    }

    .aside-left {
      left: 0;
    }

    .aside-right {
      right: 0;
    }

    .content {
      top: 50px;
      bottom: 50px;
      background-color: gray;
      overflow: auto;
    }

    .content-with-aside-left {
      left: 24%;
    }

    .content-with-aside-right {
      right: 24%;
    }

    .footer {
      bottom: 0;
      height: 50px;
      min-height: 50px;
      background-color: royalblue;
    }
</style>
<div class="overlay overlay-theme">
  <button><div class="loader">加载中...</div></button>
</div>
<div class="page">
  <div class="header">header</div>
  <div class="aside aside-left">aside left</div>
  <div class="content content-with-aside-left content-with-aside-right">content</div>
  <div class="aside aside-right">aside right</div>
  <div class="footer">footer</div>
</div>
```

