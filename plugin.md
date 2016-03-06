# 插件

插件是用于实现简单的显示及数据处理的功能扩展。插件是可以开启关闭的，但不会影响原有系统的代码；

插件结构：

插件结构图

![](images/54aa90907a9f6.png)


以Demo插件为例：

Controller //控制器目录

Model   //插件自定义模型目录
View    //模板目录，可以配置多个主题
config.php //模板配置文件

DemoPlugin.class.php 插件主文件，格式为：插件名+Plugin.class.php

README.txt 说明文件

lisense.txt 授权协议文件

