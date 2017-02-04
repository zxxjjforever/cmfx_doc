# 应用

应用就是`application`目录下的一个模块，它是独立于其它模块存在的，有自己独立的运行空间；

应用采用MVC的结构:

拿Blog应用举例:

```
Blog
  Controller 控制器目录（必备）
  Common 函数库（可选）
  Conf 配置（可选）
  Lang 多语言包（可选）
  Menu 后台菜单（可选）
  Model 模型（可选）
  nav.php 前台导航文件（可选）
```

而在 CMF 中应用的 View 是独立于应用之外的，它分为前台view 和后台view,  分别存放在 `themes/前台主题/应用名`，和 `admin/themes/后台主题/应用名`下；

创建一个Blog应用
* 在`application/Common/Conf/config.php`文件`MODULE_ALLOW_LIST`数组里加上应用名Blog
* 在`application`下创建上面讲到的`Blog`目录结构；
* 创建一个控制器,在模块`Controller`目录下创建一个`IndexController.class.php`文件

```php
<?php
namespace Blog\Controller;

use Common\Controller\HomebaseController;

class IndexController extends HomebaseController{

    // 首页
    public function index(){
      echo "this is blog index !";
    }

}
```

* 访问 [http://你的域名/index.php?g=blog&m=index&a=index;]()

> 注意控制器的命名规范：
> 
> 控制器类的命名方式是：控制器名（驼峰法，首字母大写）+Controller （如 IndexController）;
> 
> 控制器文件的命名方式是：类名+class.php（类文件后缀）（如 IndexController.class.php);

