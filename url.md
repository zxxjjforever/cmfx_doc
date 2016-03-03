# URL生成

ThinkCMF遵循 ThinkPHP 的 url 生成方法：

U方法的定义规则如下（方括号内参数根据实际应用决定）：

U('地址表达式',['参数'],['伪静态后缀'],['是否显示域名'])

U('Blog/Index/index') // 生成Blog应用Index控制器的index操作的URL地址
U('Portal/Article/index?id=1') // 生成Portal应用Article控制器的index操作 并且参数id为1的URL地址
U('Portal/Article/index',array('id'=>1) // 生成Portal应用Article控制器的index操作 并且参数id为1的URL地址
U('User/index') // 生成当前应用的User控制器的index操作的URL地址
参数：

U方法的第二个参数支持数组和字符串两种定义方式，如果只是字符串方式的参数可以在第一个参数中定义，例如：

U('Blog/Index/index',array('cat'=>1,'status'=>1))
U('Blog/Index/index','cat=1&status=1')
U('Blog/Index/index?cat=1&status=1')


添加生成带域名的 url,只要把第四个参数设置为 true

U('Blog/Index/index','cat=1&status=1',true,true)


ThinkCMF leuu/UU方法

为了配合后台设置的 url 美化规则，cmf 增加了 leuu/UU两个方法，UU方法只是 leuu 的别名用法一样；

leuu 的参数列表和  U 方法一样，只是要配合后台设置的 url美化规则才能生效，如没有规则，leuu 其实就是 U 方法；

url的美化规则设置：

进入ThinkCMF后台
后台 设置->网站信息->URL美化

原始网址规则：应用名（小写）/控制器名/操作名?参数 如：portal/list/index?id=1
显示网址：英文字母加数字，不带后缀；



如：

原始网址规则：portal/list/index?id=1

显示网址：cases

leuu("portall/list/index",array('id'=>1)) //生成的 url为/cases.html
列出常用的优化方案：
portal/list/index?id=1 news   http://demo.thinkcmf.com/news.html
portal/list/index?id=2 discovery http://demo.thinkcmf.com/discovery.html
portal/page/index?id=2 contacts http://demo.thinkcmf.com/contacts.html
portal/page/index?id=14 about http://demo.thinkcmf.com/about.html
portal/article/index article/:id\d http://demo.thinkcmf.com/article/1.html
portal/list/index list/:id\d http://demo.thinkcmf.com/list/1.html