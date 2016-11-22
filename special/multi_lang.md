# 多语言开发

## 概述
ThinkCMF已经默认开启了多语言的支持,后台以语言包形式实现多语言,前台以语言包和多模板的形式实现多语言.

######语言包
ThinkCMF开启的语言有三个,分别是zh-cn,en-us,zh-tw,此项配置在application/Common/Conf/config.php配置文件下,可以通过更改`LANG_LIST`的值增加语言.

语言包分为框架核心语言包(在simplewind/Core/Lang目录下)和应用语言包(在每个应用的Lang目录下,如application/Portal/Lang),根据你设置的语言列表,在这些地方增加相应的语言包,就实现了多语言.

应用语言包具体位置说明:

| 语言包      | 文件位置 | 加载时间|
| ---------- | -------------   | ---------------|
| 应用公共语言包         |  application/Common/Lang/语言.php | 都加载 |
| 应用语言包            |  application/应用名/Lang/语言.php | 只在访问应用时加载|
| 应用控制器语言包       |  application/应用名/Lang/语言目录/语言.php| 只在访问控制器下方法时加载
| 应用控制器后台菜单语言包|  application/应用名/Lang/语言目录/admin_menu.php| 登录后台首页,和访问后台控制器时加载|

######语言文件定义
1.语言文件格式为PHP返回数组形式,如:
```php
return array(
     'ADMIN_CENTER' => 'Admin Center', 
     'WELCOME_USER' => 'Welcome, {$username}!',
     'REFRESH_CURRENT_PAGE' => 'Refresh Current Page',
     'WEBSITE_HOME_PAGE' => 'Website Home Page'
);
```
2.也可以在代码中动态设置
```php
    L('ADMIN_CENTER','后台管理中心');
    $lang_admin_center = L('ADMIN_CENTER');
```

######变量传入支持
1.在定义语言包时也支持变量,如:
```php
return array(
    'WELCOME_USER' => 'Welcome, {$username}!',
);
```
2.在使用 L 方法获取时,可以传入$username 变量,如:
```php
    $lang_welcome_user =  L('WELCOME_USER',array('username'=>'无敌小夏'));
    echo $lang_welcome_user; // 这里输出的字符串就是:Welcome,无敌小夏!
```

######获取语言包设置的值
1.在PHP代码里使用 L 方法,如:
```php
    $lang_admin_center = L('ADMIN_CENTER');
    echo $lang_admin_center; // 这里输出的值是:Admin Center
```
2.在模板里使用 L 方法,如:
```php
    <!--以下输出的字符串也是:Admin Center-->
    {:L('ADMIN_CENTER')} 

    <!--以下输出的字符串也是:Welcome,无敌小夏!-->
    {:L('WELCOME_USER',array('username'=>'无敌小夏'))} 
```

### 前台模板多语言
ThinkCMF前台模板多语言是使用多模板的方式来实现的,如:当前模板是`simplebootx`,如果想开启英文前台模板的话,就只要加一个模板名为 `simplebootx_en-us`模板就可以了;

###### 前台模板多语言实现原理:
ThinkCMF在前台控制器加载模板文件时,会根据当前用户的浏览器语言或者用户指定的语言来加载模板文件,如果是中文用户就加载 simplebootx 里的模板文件,如果是英文用户就加载 simplebootx_en-us 里的模板文件;每个模板里数据调用是独立的,你可以在不同模板里做不同的配置,以调用不同的语言的内容;

###### 为什么选用多模板形式实现前台多语言?
很多用户会疑问,这不是会增加维护的难度吗?为什么不用语言包的形式呢?
维护难度当然会增加,做一个模板和做两个模板是不一样的时间,但你想英文模板和中文模板无论从内容还风格都有可能会不同,一个模板,你要考虑很多布局上兼容的问题,同时,如果想对不同语言的用户做不同的体验上的界面设计,一个模板肯定无法满足,所以多模板形式才是前台多语言最好的选择,当然你在模板里也可以使用应用里设置的语言包.


