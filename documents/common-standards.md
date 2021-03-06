# 前端普适性规范

## 黄金定律

坚持制定好的代码规范。

无论团队人数多少，代码应该同出一门。

### 项目命名

全部采用小写方式， 以下划线分隔，禁止驼峰式命名。

例：my\_project\_name

### 目录命名

参照项目命名规则；

有复数结构时，要采用复数命名法。

例：scripts/js, styles/css, images, data\_models

### JS文件命名

参照项目命名规则。

例：account\_model.js

### CSS, SCSS文件命名

参照项目命名规则。

例：retina\_sprites.scss

### HTML文件命名

参照项目命名规则。

不允许命名带有广告等英文的单词，例如ad,adv,adver,advertising，防止该模块被浏览器当成垃圾广告过滤掉。任何文件的命名均如此。

例：error\_report.html

## 项目文件规范（根据不同情况可做调整）

文件均归档至约定的目录中，建包格式如下：

![](http://i2.bvimg.com/627112/a32f07a2bad77791.png)

注意：

* css文件放在css文件夹中，如下图。

![](http://i2.bvimg.com/627112/0fa3989cf11a1c2b.png)

* image放在images文件夹中，为了能便捷快速的找到相应的图片资源，images文件下又氛围img和icon两个文件夹。所有图片img-，banner，背景图bg-等都放在img文件夹中。图标icon-，聚合图spr-，放在icon文件夹中，如下图。

![](http://i2.bvimg.com/627112/96e1182e484b534f.png)

* js放在js文件夹中，如下图。

![](http://i2.bvimg.com/627112/5607edb94516cd4c.png)

* 页面放在一个名为module的文件夹中。根据功能点分类建文件夹存放相应功能的页面，可参考接口文档接口的分类来建文件夹，如下图所示，app/h5（h5支持app），businesses（商户类），card（市民卡类），common（公共页面部分），generic（通用类），management（运维管理类），order（订单类），payment（支付类），static（静态展示页面），user（用户类）等，如下图。

![](http://i2.bvimg.com/627112/895b375bbcbb6688.png)

![](http://i2.bvimg.com/627112/1362866cd9fbd567.png)

