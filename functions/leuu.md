# leuu()/UU()

UU和leuu是ThinkCMF X1.2增加有url美化方法,两个用法完全一样，UU就是leuu的别名；

用法和U方法一样；对于需要美化的url要用到这个方法；



leuu方法的定义规则如下（方括号内参数根据实际应用决定）：

```php
leuu('地址表达式',['参数'],['伪静态后缀'],['显示域名'])
```

地址表达式的格式定义如下：
```php
[应用/控制器/操作#锚点@域名]?参数1=值1&参数2=值2...
leuu('portal/list/index',array('id'=>1)) 
```


leuu方法要配置后台设置的url规则才能完成url的美化；如果没有相应规则，则和U方法生成的url一样；



url的美化规则写法：
进入ThinkCMF后台
后台 设置->网站信息->URL美化

原始网址规则：应用名（小写）/控制器名/操作名?参数 如：portal/list/index?id=1
显示网址：英文字母加数字，不带后缀；

列出常用的优化方案：
```
portal/list/index?id=1 news http://demo.thinkcmf.com/news.html
portal/list/index?id=2 discovery http://demo.thinkcmf.com/discovery.html
portal/page/index?id=2 contacts http://demo.thinkcmf.com/contacts.html
portal/page/index?id=14 about http://demo.thinkcmf.com/about.html
portal/article/index article/:id\d http://demo.thinkcmf.com/article/1.html
portal/list/index list/:id\d http://demo.thinkcmf.com/list/1.html
```

![](../images/54857e9f9b316.png)