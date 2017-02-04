# 模型实例化

**为方便框架的后续升级，thinkcmf与thinkphp框架模型操作方法完全一致。
所以这里是支持thinkphp原生的M方法和D方法来实例化模型;**

实例化模型的好处：
可以实现自动完成，自动校验功能。使用模型封装的方法。分离M层和C层；

## M方法：
M(['模型名'],['数据表前缀'],['数据库连接信息']);
```php
//实例化模型
$User=M('User');
// 执行具体的数据操作
$User->select();
```
M方法仅支持基本的CURD操作;但是性能会较D方法高。
*如果你的模型类有自己的业务逻辑，M方法是无法支持的，就算是你已经定义了具体的模型类，M方法实例化的时候是会直接忽略。*
**M方法的特殊用法：**
$model=M();//实例化空模型；

$model->query('select * from cmf_user where id=1');//使用原生sql语句进行查询id为1的用户

## D方法:
假设当前模块为Home;
D('User');D('Home/User');是一样的；

如果在Linux环境下面，一定要注意D方法实例化的时候的模型名称的大小写。
D方法可以自动检测模型类，如果存在自定义的模型类，则实例化自定义模型类，如果不存在，则会实例化系统的\\Think\\Model基类，同时对于已实例化过的模型，不会重复实例化。
D方法的参数就是模型的名称，并且和模型类的大小写定义是一致的，例如：
参数	实例化的模型文件
User	对应的模型类文件的 \Home\\Model\\UserModel.class.php
UserType	对应的模型类文件的 \\Home\\Model\\UserTypeModel.class.php

用法示例:
```php
//实例化模型
$User = D('User');
// 相当于 $User = new \\Home\\Model\\UserModel();
// 执行具体的数据操作
$User->select();
//$User->diy_select();//diy_select方法是您在\\Home\\Model\\UserModel.class.php中自定义的方法。
```

*当 \\Home\\Model\\UserModel 类不存在的时候，D函数会尝试实例化公共模块下面的 \\Common\\Model\\UserModel 类*
D方法还可以支持跨模块调用，需要使用：
```php
//实例化Admin模块的User模型
D('Admin/User');
//实例化Extend扩展命名空间下的Info模型
D('Extend://Editor/Info');
```

*注意：跨模块实例化模型类的时候 不支持自动加载公共模块的模型类*

#### M方法和D方法的区别
1. M方法不用加载具体模型类效率更高。但仅能实现基础的CURD;
2. D方法会先实例化具体的模型类，找不到后自动调用M方法来实例化模型类


*名词解释*
1. CURD(Create,Update,Read,Delete),数据库的增删查改操作

*参考文献：*
1. http://www.kancloud.cn/manual/thinkphp/1729
