# CSS规范

## 1、命名规范

### 使用类选择器，尽量避免使用ID选择器定义样式

ID在一个页面中的唯一性导致了如果以ID为选择器来写CSS，就无法重用。

### 以字母开头

* 必须以字母开头命名选择器，这样可保证在所有浏览器下都能兼容；
* 不允许单个字母的类选择器出现；
* 不允许命名带有广告等英文的单词，例如ad,adv,adver,advertising，已防止该模块被浏览器当成垃圾广告过滤掉。任何文件的命名均如此。

### 全小写，并使用 ' - ' 连字符

* 下划线 ' \_ ' 禁止出现在class命名中，统一使用'-'连字符
* 禁止驼峰式命名

### 命名应简约而不失语义

* 避免过度简写，.ico足够表示这是一个图标，而.i不代表任何意思
* 使用有意义的名称，使用结构化或者作用目标相关的，而不是抽象的名称

### 文件命名举列

* 基本样式：`base.css`
* 框架布局：`layout.css`
* 模块样式：`module.css`
* 全局样式：`global.css`
* 字体样式：`font.css`
* 首页样式：`index.css`
* 链接样式：`link.css`
* 打印样式：`print.css`

### 常用类/ID命名举列

常用类的命名应尽量以常见英文单词为准，做到通俗易懂，并在适当的地方加以注释。 部分命名解释约定：

整页`.wp`页眉`.header`页脚`.footer`导航`.nav`主体内容`.main`侧边栏`.side`标志`.logo`搜索`.search`登录`.login`注册`.reg`标题`.tit-...`副标题`.subtit-...`按钮`.btn-...`链接`.link-...`背景图片`.bg-...`列表`.list-...`表格`.tb-...`标签`.tag-...`视频`.video-...`联系`.contact`

### Reset参考

`注意！`使用时，按需配置，去除冗余

#### 精简版（适用于一般的游戏类官网、专题）

```css
body,h1,h2,h3,h4,h5,h6,p,ul,ol,li,input,select,textarea,div,table,td,th,tr,dt,dd,dl{margin:0;padding:0;}
h1,h2,h3,h4,h5,h6{font-size:100%;font-weight:normal;}
ul,ol{list-style:none;}
strong,b{font-weight:normal;}
em,i{font-style:normal;}
table{border-spacing:0;border-collapse:collapse;}
img{border:0;vertical-align:middle;}
input,select{vertical-align:middle;font-size:100%;line-height:150%;font-family:arial,'\5FAE\8F6F\96C5\9ED1',sans-serif;-webkit-appearance:none;}
a{text-decoration:none;outline:none;hide-focus:expression(this.hideFocus=true);background-color:transparent;-webkit-tap-highlight-color:transparent;}
body{min-width:1000px;font:14px/1.5 arial,"\5FAE\8F6F\96C5\9ED1",sans-serif;-webkit-text-size-adjust:none;-ms-text-size-adjust:none;}
```

#### 通用版（基本适用于所有的页面）

```css
body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,code,form,fieldset,legend,input,textarea,p,blockquote,th,td{margin:0;padding:0}
table{border-collapse:collapse;border-spacing:0}
fieldset,img{border:0}
address,caption,cite,code,dfn,em,strong,th,var{font-style:normal;font-weight:normal}
ol,ul{list-style:none}
caption,th{text-align:left}
h1,h2,h3,h4,h5,h6{font-size:100%;font-weight:normal}
q:before,q:after{content:''}
abbr,acronym{border:0;font-variant:normal}
sup{vertical-align:text-top}
sub{vertical-align:text-bottom}
input,textarea,select{font-family:inherit;font-size:inherit;font-weight:inherit}
input,textarea,select{*font-size:100%}
```

#### 通用版（支持html5）

```css
body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,code,form,fieldset,legend,input,textarea,p,blockquote,th,td,hr,button,article,aside,details,figcaption,figure,footer,header,hgroup,menu,nav,section{margin:0;padding:0}
article,aside,details,figcaption,figure,footer,header,hgroup,menu,nav,section { display:block; }
table{border-collapse:collapse;border-spacing:0}
audio,canvas,video { display: inline-block;*display: inline;*zoom: 1;}
fieldset,img{border:0}
address,caption,cite,code,dfn,em,strong,th,var{font-style:normal;font-weight:normal}
ol,ul{list-style:none}
caption,th{text-align:left}
h1,h2,h3,h4,h5,h6{font-size:100%;font-weight:normal}
q:before,q:after{content:''}
abbr,acronym{border:0;font-variant:normal}
sup{vertical-align:text-top}
sub{vertical-align:text-bottom}
input,textarea,select{font-family:inherit;font-size:inherit;font-weight:inherit}
input,textarea,select{*font-size:100%}
```

## 2、代码风格

使用4个空格做为缩进，部分内容为可选

### css属性值需要用到引号时，统一使用单引号

```css
/* 不推荐 */
selectors{ font-family:"\5FAE\8F6F\96C5\9ED1";}

/* 推荐 */
selectors{ font-family:'\5FAE\8F6F\96C5\9ED1';}
```

### 为单个css选择器或新申明开启新行

```css
/* 不推荐 */
.home-count .hd,.content-title,.select-game-title .title{}.nav{}

/* 推荐 */
.home-count .hd,
.content-title,
.select-game-title .title{}
.nav{}
```

### css属性书写顺序

建议遵循：布局定位属性 自身属性 文本属性 其他属性 CSS3属性[mozilla官方属性顺序推荐](http://www.mozilla.org/css/base/content.css)

```css
/*  这些属性只是最常用到的, 并不代表全部 */
/* 布局定位属性 */
display / list-style / position（相应的 top,right,bottom,left） / float / clear  / visibility / overflow

/* 自身属性 */
width / height / margin / padding / border / background

/* 文本属性 */
color / font / text-decoration / text-align / vertical-align / white- space / break-word

/* 其他（CSS3）  */
content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient ...
```

### css浏览器私有前缀书写格式

私有在前，标准在后。先写带有浏览器私有标志的，后写W3C标准的。

```css
selectors{
    background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#ffffff), color-stop(100%,#eff2f4));
    background: -webkit-linear-gradient(top, #ffffff 0%,#eff2f4 100%);
    background: -moz-linear-gradient(top, #ffffff 0%, #eff2f4 100%);
    background: -ms-linear-gradient(top, #ffffff 0%,#eff2f4 100%);
    background: -o-linear-gradient(top, #ffffff 0%,#eff2f4 100%);
    background: linear-gradient(to bottom, #ffffff 0%,#eff2f4 100%);
    filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#ffffff', endColorstr='#eff2f4',GradientType=0 );
}
```

### 不要以没有语义的标签作为选择器

这会造成大面积污染，除非你可以断定现在或将来你的这个选择器不会污染其他同类

```css
/* 推荐 */
.m-xxx div{ ... }
```

### css单行书写法（根据个人习惯选择）

每个CSS选择符的主申明区中的属性在同一行内书写，每个属性之间空一格

```css
selectors{ height: 30px; padding-bottom: 10px; border-bottom: 1px solid #858585; margin-bottom: 10px; }
```

### css多行书写法（根据个人习惯选择）

每个CSS选择符的主申明区中的每一条属性新起一行

```css
selectors{
    height: 30px;
    padding-bottom: 10px;
    border-bottom: 1px solid #858585;
    margin-bottom: 10px;
}
```

### 用CSS控制交互或视觉的变化，JS只需要增减className

* 利用CSS一次性更改多个节点样式，避免多次渲染，提高渲染效率。
* 需要在结构中注释此类交互。

## 3、注释

### 行间注释

直接写于属性值后面，如：

```css
.search{background: #333 url(../img/search.gif) no-repeat;/*定义搜索框的背景*/}
```

### 整段注释

分别在开始及结束地方加入注释，如：

```css
/*=====搜索条=====*/
.search {background: #333 url(../img/search.gif) no-repeat;}
/*=====搜索条结束=====*/
```

注意：以下写法不可取

```css
.news/* 这里是高度自动撑 */ {line-height:1.5}
.news {/*line-height:1.5 这里是高度自动撑 */}
```

理由很简单，注释是ie6的hack方法之一，所以这样写容易让ie6误解。

`提示`：尽量不要使用中文注释，无论是html也好 css js也罢，因为会导致神奇的IE6出现无法预测的问题。尽量使用简单的英文，拼音也好。在版本发布的时候，尽量剔除注释内容，尽可能的减少文件的字节数。

## 4、Hack

原则上不允许使用Hack - 很多不兼容问题可以通过改变方法和思路来解决，并非一定需要Hack，根据经验你完全可以绕过某些兼容问题。 - 一种合理的结构和合理的样式，是极少会碰到兼容问题的。 -由于浏览器自身缺陷，我们无法避开的时候，可以允许使用适当的Hack。

### 统一Hack方法

```css
.element{
    color:#000;             /*w3c标准*/
    [;color:#f00;];         /*Webkit(chrome和safari)*/
    color:#666\9;           /*IE8*/
    *color:#999;            /*IE7*/
    _color:#333;            /*IE6*/
}
:root .element{color:#0f0\9;}  /*IE9*/
@media all and (-webkit-min-device-pixel-ratio:10000), not all and (
-webkit-min-device-pixel-ratio:0) { .element{color:#336699;}}  /*opera*/
@-moz-document url-prefix(){ .element{color:#f1f1f1;}} /*Firefox*/
```

### 简写css颜色属性值

```css
/* 不推荐 */
selectors{ color:#000000; background-color:#ddeeff;}

/* 推荐 */
selectors{ color:#000; background-color:#def;}
```

### 删除css属性值为0的单位

0就是0，任何单位都不需要[w3c关于属性单位的说明](http://www.ietf.org/rfc/rfc4646.txt)

```css
/* 不推荐 */
selectors{ margin:0px; padding:0px;}

/* 推荐 */
selectors{ margin:0; padding:0;}
```

### 删除无用CSS样式

* 第一，删除无用的样式后可以缩减样式文件的体积，加快资源下载速度；
* 第二，对于浏览器而言，所有的样式规则的都会被解析后索引起来，即使是当前页面无匹配的规则。移除无匹配的规则，减少索引项，加快浏览器查找速度；

```css
/* 不推荐 */
selectors{ font-size:12px;}
.nav{}
.nav-item{ height:20px;}

/* 推荐 */
selectors{ font-size:12px;}
.nav-item{ height:20px;}
```



