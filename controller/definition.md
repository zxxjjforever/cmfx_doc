# 控制器定义

ThinkCMF目前分为两种控制器，前台和后台控制器；

无论是前台，还是后台控制器都位于应用的 Controller目录下.



前台控制器一般继承 Common\Controller\HomebaseController,如果你需要用户登录才访问或操作此控制器，就要继承 Common\Controller\MemberbaseController；

我们来创建一个前台控制器：

在Blog应用Controller目录下创建一个IndexController.class.php文件

<?php

namespace Blog\Controller;
use Common\Controller\HomebaseController;
class IndexController extends HomebaseController{
    public function index(){
      echo "this is blog index !";
    }
}
访问地址：http://你的域名/?g=blog&m=index&a=index;

如果只让用户在登录时才能访问此控制器，只需把HomebaseController换成MemberbaseController；

<?php

namespace Blog\Controller;
use Common\Controller\MemberbaseController;
class IndexController extends MemberbaseController{
    public function index(){
      echo "this is blog index !";
    }
}
这里 IndexController 下的所有方法，用户只能在登录后才能访问，否则会报错，让用户登录；



创建后台控制器：

在Blog应用Controller目录下创建一IndexadminController.class.php文件（注意：这里有文件命名规则，以****adminController.class.php或 Admin***Controller.class.php命名的是后台Controller, 在后台菜单导入时会自动识别；）

```
<?php
namespace Blog\Controller;
use Common\Controller\AdminbaseController;

class IndexadminController extends AdminbaseController{
    public function index(){
        echo "this is admin controller!";
    }
}
```
访问地址：http://你的域名/?g=blog&m=indexadmin&a=index，这里你一定要先登录后台，才能访问；

如果你想这个控制不用管理员登录也能被访问到，只给IndexadminController加个空的_initialize()方法；

<?php
namespace Blog\Controller;
use Common\Controller\AdminbaseController;

class IndexadminController extends AdminbaseController{

    //初始化，这里不执行父类的初始化方法
    public function _initialize(){}
    
    public function index(){
        echo "this is admin controller!";
    }
}