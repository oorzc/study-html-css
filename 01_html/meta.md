# 常用meta整理
---
```html
  <meta charset="utf-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
  <meta name="renderer" content="webkit" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0,maximum-scale=1.0, user-scalable=no"/>
  <meta name="keywords" content="xx,yy,zz" />
  <meta name="description" content="xxx " />
```

* 忽略数字自动识别为电话号码
`<meta content="telephone=no" name="format-detection" /> `

* 忽略识别邮箱
`<meta content="email=no" name="format-detection" />`

* 页面重定向：content内的数字代表时间（秒），即多少时间后刷新。如果加url，则会重定向到指定网页（搜索引擎能够自动检测）
```html
<meta http-equiv="refresh" content="0;url=" />
```

* 其他
```html
<!-- 针对手持设备优化，主要是针对一些老的不识别viewport的浏览器，比如黑莓 -->
<meta name="HandheldFriendly" content="true">
<!-- 微软的老式浏览器 -->
<meta name="MobileOptimized" content="320">
<!-- uc强制竖屏 -->
<meta name="screen-orientation" content="portrait">
<!-- QQ强制竖屏 -->
<meta name="x5-orientation" content="portrait">
<!-- UC强制全屏 -->
<meta name="full-screen" content="yes">
<!-- QQ强制全屏 -->
<meta name="x5-fullscreen" content="true">
<!-- UC应用模式 -->
<meta name="browsermode" content="application">
<!-- QQ应用模式 -->
<meta name="x5-page-mode" content="app">
<!-- windows phone 点击无高光 -->
<meta name="msapplication-tap-highlight" content="no">
```

&lt;meta&gt; 元素可提供有关页面的元信息（meta-information），比如针对搜索引擎和更新频度的描述和关键词。

&lt;meta&gt; 标签位于文档的头部，不包含任何内容。&lt;meta&gt; 标签的属性定义了与文档相关联的名称/值对。

**必要属性**

| 属性 | 值 | 描述 |
| :--- | :--- | :--- |
| content | some text | 定义与http-equiv或name相关的属性 |

**可选属性**

| 属性 | 值 | 描述 |
| :--- | :--- | :--- |
| http-equiv | content-type/expire/refresh/set-cookie | 把content属性关联到HTTP头部 |
| name | author/description/keywords/generator/revised/others | 把content属性关联到一个名称 |
| content | some text | 定义用于翻译content属性值的格式 |

### SEO优化 {#articleHeader2}

* 页面关键词：每个页面应具有描述该网页内容的一组唯一的关键字，使用人们可能会搜索，并准确描述网页上所提供信息的描述性和代表性关键字及短语。标记不应超过874个字符。

```
<meta name="keywords" content="your tags" />
```

* 页面描述，每个网页都应有一个补超过150个字符且能准确反映网页内容的描述标签

```
<meta name="description" content="150 words" />
```

* 搜索引擎索引方式：robotterms是一组使用逗号（,）分割的值，通常有如下几种取值：none，noindex，nofollow，all，index和follow。确保正确使用nofollow和noindex属性值

```
<meta name="robots" content="index,follow" />
<!--
    all：文件将被检索，且页面上的链接可以被查询；
    none：文件将不被检索，且页面上的链接不可以被查询；
    index：文件将被检索；
    follow：页面上的链接可以被查询；
    noindex：文件将不被检索；
    nofollow：页面上的链接不可以被查询。
 -->
```

* 其他
```
<meta name="author" content="author name" /> <!-- 定义网页作者 -->
<meta name="google" content="index,follow" />
<meta name="googlebot" content="index,follow" />
<meta name="verify" content="index,follow" />
```

### 移动设备 {#articleHeader3}
* viewport：能优化移动浏览器的显示。如果不是响应式网站，不要使用initial-scale或者禁用缩放。
大部分4.7-5寸设备的viewport宽设为360px；5.5寸设备设为400px；iphone6设为375px；ipone6 plus设为414px。

```
 <meta name="viewport" content="width=device-width, initial-scale=1.0,maximum-scale=1.0, user-scalable=no"/>
```
1. width：宽度（数值 / device-width）（范围从200 到10,000，默认为980 像素）
2. height：高度（数值 / device-height）（范围从223 到10,000）
3. initial-scale：初始的缩放比例 （范围从>0 到10）
4. minimum-scale：允许用户缩放到的最小比例
5. maximum-scale：允许用户缩放到的最大比例
6. user-scalable：用户是否可以手动缩 (no,yes)
7. minimal-ui：可以在页面加载时最小化上下状态栏。（已弃用）

* WebApp全屏模式：伪装app，离线应用。
`<meta name="apple-mobile-web-app-capable" content="yes" /> <!-- 启用 WebApp 全屏模式 -->`

* 隐藏状态栏/设置状态栏颜色：只有在开启WebApp全屏模式时才生效。content的值为default | black | black-translucent 。
`<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent" />`

* 添加到主屏后的标题
`<meta name="apple-mobile-web-app-title" content="标题">`

* 添加智能 App 广告条 Smart App Banner：告诉浏览器这个网站对应的app，并在页面上显示下载banner(如下图)。参考文档
`<meta name="apple-itunes-app" content="app-id=myAppStoreID, affiliate-data=myAffiliateData, app-argument=myURL"> `
![](http://qiniu.sponges.cn/201802242021_455.png?imageView2/0/w/680/h/480)

### 网页相关 {#articleHeader4}

申明编码

```
<meta charset='utf-8' />
```

* 优先使用IE最新版本和chrome

```
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
```

* 浏览器内核检测

国内浏览器很多都是双内核（webkit和Trident），webkit内核高速浏览，IE内核兼容网页和旧版网站。而添加meta标签的网站可以控制浏览器选择何种内核渲染

```
 <meta name="renderer" content="webkit|ie-comp|ie-stand">
```

国内双核浏览器默认内核模式如下：

1. 搜狗高速浏览器、QQ浏览器：IE内核（兼容模式）

2. 360极速浏览器、遨游浏览器：Webkit内核（极速模式）

禁止浏览器从本地计算机的缓存中访问页面内容

```
<meta http-equiv="Pragma" content="no-cache">
```

* window8

```
<meta name="msapplication-TileColor" content="#000"/> <!-- Windows 8 磁贴颜色 -->
<meta name="msapplication-TileImage" content="icon.png"/> <!-- Windows 8 磁贴图标 -->
```

* 站点适配：主要用于PC-手机页的对应关系

```
<meta name="mobile-agent"content="format=[wml|xhtml|html5]; url=url">
<!--
[wml|xhtml|html5]根据手机页的协议语言，选择其中一种；
url="url" 后者代表当前PC页所对应的手机页URL，两者必须是一一对应关系。
 -->
```

* 转码声明：用百度打开网页可能会对其进行转码（比如贴广告），避免转码可添加如下meta

```
<meta http-equiv="Cache-Control" content="no-siteapp" />
```

---

参考:

https://segmentfault.com/a/1190000002407912
