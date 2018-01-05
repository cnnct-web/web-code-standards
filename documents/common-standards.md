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

例：error\_report.html

## 项目文件规范（根据不同情况可做调整）

文件均归档至约定的目录中，建包格式如下：

![](/assets/import.png)

注意：

* css文件放在css文件夹中，如下图。

![](/assets/import3.png)

* image放在images文件夹中，为了能便捷快速的找到相应的图片资源，images文件下又氛围img和icon两个文件夹。所有图片img-，banner，背景图bg-等都放在img文件夹中。图标icon-，聚合图spr-，放在icon文件夹中，如下图。

![](/assets/import4.png)

* js放在js文件夹中，如下图。

![](/assets/import5.png)

* 页面放在一个名为module的文件夹中。根据功能点分类建文件夹存放相应功能的页面，可参考接口文档接口的分类来建文件夹，如下图所示，app/h5（h5支持app），businesses（商户类），card（市民卡类），common（公共页面部分），generic（通用类），management（运维管理类），order（订单类），payment（支付类），static（静态展示页面），user（用户类）等，如下图。

![](/assets/import6.png)

![](/assets/import7.png)

