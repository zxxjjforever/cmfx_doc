# 安装使用

上传你的代码，直接在浏览器中输入你的域名或IP（例如：www.yourdomain.com）,安装程序会自动执行安装。期间系统会提醒你输入数据库信息以完成安装，安装完成后建议删除application目录下的Install。

安装完成，一定把 data/conf/db.php 文件做个备份！否则大神也救不了你！

ThinkCMF目录结构：

```php
|--admin                                /管理后台URL重定向目录，你可以将文件夹名改为任何你喜欢的

    |--themes                      /后台模板文件目录

|--api                                    /主要是放 ucenter

|--application                        /应用目录

|--data                                  /各类数据存放目录，包括缓存数据

|--simplewind                        /核心包，无特殊情况请勿改动

|--public                               /静态文件存放包，包含bootstrap资源

|--themes                                     /前台模板文件目录             
```        

application 目录结构：

|--application 

            |--Admin                    /后台管理应用

            |--Api                        /公共接口

            |--Asset                    /资源管理应用

            |--Comment                /评论应用

            |--Common                /应用公共模块

            |--Portal                    /门户应用

应用的目录结构规范：

举例应用Portal

|--Portal

            |--Controller                    /必须目录，存放应用的操作模块如：/IndexController.class.php

            |--Conf                      /可选，应用配置文件存放目录，如应用无配置文件则不需要

            |--Common                /可选，应用函数库，如无则不需要

