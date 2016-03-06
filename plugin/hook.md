# 插件钩子

钩子是插件执行的触发器；插件就像挂在钩子上的东西；

插件只有实现相应钩子方法，并安装启用成功后才能执行；



ThinkCMF系统内置了很多钩子；http://www.thinkcmf.com/document/hooks.html 

开发者也可以用hook('test')方法在控制器只加入钩子，让你的应用具有更好的扩展性；

同时也可以模板里加入钩子{:hook('footer')}；

钩子也支持传入参数hook('footer',array('test'=>1));





向系统暴露你的钩子

就是把你的钩子在相应的文件里列出来，系统会来检测。
暴露应用控制器钩子：

在你的应用根目录加上hooks.php文件

文件中返回此应用所有钩子数组就可以了；

如portal应用：

untitled1.png

hooks.php文件内容

<?php
return array(
		//'test',
);
暴露你的模板钩子：

在你的模板根目录加上hooks.html文件；

在此文件中用英文逗号分开此模板所有的钩子就可以了；

如simplebootx模板：

untitled1.png

hooks.html文件内容：

footer,footer_end