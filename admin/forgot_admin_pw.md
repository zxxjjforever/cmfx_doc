# 忘记后台密码？

后台密码忘记了怎么办？

1.如果你已经在后台配置了，邮件发送功能且邮箱是你的真实邮箱，可以到前台登录页找回密码；

2.如果你是后台管理员，你可以使用 sp_password()方法生成一下新的密码；

你只要在任何一个前台可以访问控制器里,如application/Portal/Controller/IndexController.class.php

```php
namespace Portal\Controller;
use Common\Controller\HomebaseController; 
/**
 * 首页
 */
class IndexController extends HomebaseController {
	
    public function index() {
        echo sp_password('666666');//这次一定要记清了，密码是6个6；
        exit;
    	$this->display(":index");
    }

}```
访问你的首页：得到密码后，把你刚刚修改的地方还原；

打开你的数据库管理功能，找到你的管理员那一列，把密码换进去！



3.如果以上方法都不行，那你只能找 ThinkCMF的官网人员了(如：Dean),不过他的收费很高，单次还原密码要1000元，看到这里你估计不会考虑了！

ps:让以后你还忘记密码！

开源不容易，多少给点支持行不？别删链接呀也！