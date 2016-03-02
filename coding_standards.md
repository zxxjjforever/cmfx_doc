# 开发规范

ThinkCMF完全按ThinkPHP开发规范进行

开发前请详细阅读：

http://document.thinkphp.cn/manual_3_2.html#develop_standard

##ThinkCMF特别开发规范

应用后台控件器放在应用Controller目录中，最好不要存放在Admin/Controller下，保证应用模块独立

应用后台控件器命名

以****adminController.class.php或者Admin****Controller.class.php命名的是后台Controller, 在后台菜单导入时会自动识别

应用后台控件器方法命名：

用户无法访问的内部方法，请以下划线（_）开头；

附件保存路径，要相对于upload目录，只保存之后路径

使用I函数获取post和get的数据

模板中php代码注释都使用/**/的方式，//这种方式一定不要用，否则debug关闭后会有各种问题！

各种php文件最好别加?>结束，防止响应多余字符

