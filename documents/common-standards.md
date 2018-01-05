# 前端普适性规范

## 黄金定律

不管有多少人共同参与同一项目，一定要确保每一行代码都像是同一个人编写的。

## 项目命名

项目名全部采用小写方式，以下划线分隔，禁止驼峰式命名。比如：my\_project\_name

## 文件命名

文件命名参照项目命名规则。比如: error\_report.html

有复数结构时，要采用复数命名法，比如： scripts, styles, images, data\_models

文件名中只可由小写英文字母 az 、排序数字 09 或间隔符 \_ 组成，禁止包含特殊符号，比如空格、$ 等

为了醒目，某些说明文件的文件名，可以使用大写字母，比如: README, LICENSE

为更好的表达语义，文件名使用英文名词命名，或英文简写。

不允许命名带有广告等英文的单词，例如ad,adv,adver,advertising，防止该模块被浏览器当成垃圾广告过滤掉。任何文件的命名均如此。

文件常用命名:

* index.html 引导页&首页

* main.html 首页

* download.html 下载页面

* act.html 活动列表页面

* video.html 视频

* cdkey.html CDKEY页面

* base.css 基本样式

* layout.css 框架布局

* module.css 模块样式

* global.css 全局样式

* font.css 字体样式

* index.css 首页样式

* link.css 链接样式

* print.css 打印样式

## 项目文件规范

文件均归档至约定的目录中，建包格式如下：

![](/assets/import.png)

注意：

css文件放在css文件夹中

![](/assets/import3.png)

image放在images文件夹中，为了能便捷快速的找到相应的图片资源，images文件下又氛围img和icon两个文件夹。所有图片img-，banner，背景图bg-等都放在img文件夹中。图标icon-，聚合图spr-，放在icon文件夹中。

![](/assets/import4.png)

js放在js文件夹中。

![](/assets/import5.png)

页面放在一个名为module的文件夹中。根据功能点分类存放不同的页面，如下所示，app/h5（h5支持app），businesses（商户类），card（市民卡类），common（公共页面部分），generic（通用类），management（运维管理类），order（订单类），payment（支付类），static（静态展示页面），user（用户类）等。

![](/assets/import6.png)

