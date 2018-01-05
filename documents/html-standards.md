# HTML规范

## 1、代码规范

### 所有html代码小写

所有代码只使用小写：适用于标签名，类名，标签的属性及属性值（text/CDATA例外，作为内容时例外）

```
<ul class="news-list"><li></li><li></li></ul>
```

### 使用html5的doctype

```
<!doctype html>
```

### 页面编码使用gbk

```
<meta charset="gbk">
```

由于互娱业务系统的特殊性，编码类型建议优先使用gbk，gbk编码是`gb2312`的扩展，并且向后兼容，具有更好的兼容性。 已采用

`gb2312`编码的项目暂不用修改，部分官网为了兼容某些特殊字符，采用`gb18030`编码，如iGame官网。 面向港澳台用户的站点可采用`big5`编码，在系统允许的前提下可采用`utf-8`编码。

### 页面内容lang为zh-Hans-CN

```
<html lang="zh-Hans-CN">
```

这条规范基于国际标准[RFC 4646](http://www.ietf.org/rfc/rfc4646.txt)，使用单一的`zh`和`zh-CN`均属于废弃用法。 与中文有关的`lang`值如下：

* `zh-Hans`简体中文
* `zh-Hans-CN`大陆地区使用的简体中文
* `zh-Hans-HK`香港地区使用的简体中文
* `zh-Hans-MO`澳门使用的简体中文
* `zh-Hans-SG`新加坡使用的简体中文
* `zh-Hans-TW`台湾使用的简体中文
* `zh-Hant`繁体中文
* `zh-Hant-CN`大陆地区使用的繁体中文
* `zh-Hant-HK`香港地区使用的繁体中文
* `zh-Hant-MO`澳门使用的繁体中文
* `zh-Hant-SG`新加坡使用的繁体中文
* `zh-Hant-TW`台湾使用的繁体中文

### 页面头部说明注释

必须在`head`区域中加上对页面相关人员注释，方便在产品环境中的查看

```
<!-- 页面设计：xxx | 页面制作：xxx | 制作时间：xxxx-xx-xx -->
```

### include语句

include中的地址为相对地址，不能使用绝对地址。被include的文件后缀可以是:`.html`或者`.inc`。

```
<!--#include virtual="/xxxx.html" -->
```

目前.htm或者.shtml文件中都可以使用include

## 2、文件命名

* index.shtml 引导页&首页
* main.shtml 首页
* download.shtml 下载页面
* act.shtml 活动列表页面
* video.shtml 视频
* cdkey.shtml CDKEY页面
* wallpaper.shtml 壁纸页面
* 文件名中只可由英文字母`a~z`、排序数字`0~9`或间隔符`-`组成。
* 件名中禁止包含特殊符号，比如`空格`、`$`等
* 文件名区分大小写，统一使用小写字母
* 为更好的表达语义，文件名使用英文名词命名，或英文简写。

## 3、图片

图片统一存放在图片服务器，注意修饰性图片与内容类图片分开放置，如：图片存放的文件夹建议用img命名来存放logo、合并的图片等页面固定元素的图片，images放一些开发会动态调用的头像、剧照图等。

### 图片格式/大小

图片格式：图片允许采用gif/jpg/png/wep ，平衡图片质量与文件大小，适当运用`css sprite`理念合并修饰类图片，不过分损失质量情况下尽量减小页面下载数据量。 图片单张体积不能超过150K，jpg图片必须压缩，一般60%品质即可，如果图片质量不好，可提高到80%

### 图片引用

* 图片路径需要使用绝对路径方式;
* 旧版页面中CSS维护仍可在webplat采用相对路径方式修改发布（备注）;
* 所有img元素必须加上alt属性，修饰性图片alt属性内容留空，内容性质图片alt属性写相应内容;

必须加上width和height属性，值为它的原大小，但不要用来对它进行缩放。

```
<img src="http://ossweb-img.qq.com/images/helper/v2/logo.png" width="172" height="72" alt="Q游助手">
```

### 图片命名图片后缀命名一律小写。

* 使用间隔符`-`进行连接。
* 一般背景图片以`bg-`开头
* 测试图片以`img-`开头
* 按钮图片以`btn-`开头
* 图标图片以`icon-`开头
* 聚合图以`spr-`开头，后跟英文单词，不推荐使用汉语拼音，如果名称过长，适当使用缩写

```
bg-body.jpg / spr-home.png / img-promo.jpg / btn-submit.png / icon-game.png
```

### 图片服务器

图片必须上传至图片服务器，CSS文件和JS文件可以按需处理。

图片服务器域名为[`http://ossweb-img.qq.com/`](http://ossweb-img.qq.com/)和[`http://game.gtimg.cn/`](http://game.gtimg.cn/)，推荐使用后者。

```
<!--不推荐-->
http://ossweb-img.qq.com/images/项目名称/xxx

<!--推荐-->
http://game.gtimg.cn/images/项目名称/xxx
```

## 4、注释

正确的注释规范：

感叹号后面2个横线，结束时2个横线； 不要在注释内容中使`--`，`--`只能发生在XHTML注释的开头和结束，也就是说，在内容中它们不再有效。 例如下面的代码是错误的:

```
<!--这里是注释     -这里是注释-->
<!--    -这里是注释     -这里是注释    --->
```

用等号或者空格替换内部的虚线,这样是正确的

```
<!--这里是注释============这里是注释-->
```

IE条件注释（IE10已不支持条件注释）

```
<!-- [if IE]>
这里只有ie浏览器才可以显示
<![endif]-->

<!-- [if !IE]>
这里只有非ie浏览器才可以显示
<! <![endif]-->

<!--[if IE 6]>
这里只有ie6浏览器才可以显示
<![endif]-->

<!--[if lt IE 9]>
这里只有ie9以下浏览器才可以显示
<![endif]-->

<!--[if lte IE 8]>
这里只有ie8以及ie8以下浏览器才可以显示
<![endif]-->
```

### 脚本中文转unicode

为防止外链脚本未申明正确编码导致乱码的问题，脚本中如用到中文，必须转为[unicode码](http://app.baidu.com/app/enter?appid=409757)

```
/* 不推荐 */
document.write("关于腾讯游戏")

/* 推荐 */
document.write("\u5173\u4e8e\u817e\u8baf\u6e38\u620f")
```

### 去掉类型属性

不要为CSS、JS使用类型属性，特别说明类型（type）属性是多余的，在HTML5中默认已包含

```
<!--不推荐-->
<link href="../css/comm.css" rel="stylesheet" type="text/css" />
<script type="text/javascript"><!--mce:0--></script>
<script src="common.js" type="text/javascript">

<!--推荐-->
<link href="../css/comm.css" rel="stylesheet" />
<script type="text/javascript"><!--mce:1--></script>
<script src="common.js">
```

### 去掉自闭合元素'/'闭合符

为半闭合元素加上'/'闭合符是没必要的，申明为html5的doctype后，所有浏览器都会正确处理，常见的半闭合元素：img input hr br

```
<!--不推荐-->
<br /><hr /><img src="/wiki/" /><input type="text" />

<!--推荐-->
<br ><hr ><img src="/wiki/" ><input type="text" >
```

### 对“&lt;”“&gt;”之类的符号进行实体转义

在 HTML 中不能使用小于号（&lt;）和大于号（&gt;），这是因为浏览器会误认为它们是标签。如果希望正确地显示预留字符，我们必须在 HTML 源代码中使用字符实体（character entities）

```
<!--不推荐-->
<a href="/wiki/">more>></a>

<!--推荐-->
<a href="/wiki/">more&gt;&gt;</a>
```

### 元素嵌套规范

段落元素与标题元素只能嵌套内联元素

```
<!--不推荐-->
<a><p> </p><div></div><p> </p></a>  <h2><div></div></h2>

<!--推荐-->
<p><span><span> </span></span></p>
<h2><span> </span></h2>
```



