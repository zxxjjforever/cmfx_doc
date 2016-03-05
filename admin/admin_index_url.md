# 后台地址是啥？
后台地址是啥？

1.thinkcmf 默认后台地址是/admin

2.如果在后台开启后台地址加密码的功能，那地址就是/?g=admin&upw=系统为你生成的加密码
![](../images/j_0012.gif)
![](../images/j_0008.gif)

后台地址加密码开启了，但我没有记呀？

没办法其实 Dean 也无能为力呀！

好吧...我太好了

1.打开 data/conf/config.php文件，记得别用 windows 的记事本打开

2.找到SP_SITE_ADMIN_URL_PASSWORD，复制它的值

3.访问/?g=admin&upw={你第二步得到的值}
