# 多语言开发

ThinkCMF已经默认开启了多语言的支持,后台以语言包形式实现多语言,前台以语言包和多模板的形式实现多语言.

######语言包
ThinkCMF开启的语言有三个,分别是zh-cn,en-us,zh-tw,此项配置在application/Common/Conf/config.php配置文件下,可以通过更改`LANG_LIST`的值增加语言.

语言包分为框架核心语言包(在simplewind/Core/Lang目录下)和应用语言包(在每个应用的Lang目录下,如application/Portal/Lang),根据你设置的语言列表,在这些地方增加相应的语言包,就实现了多语言.

######语言文件定义

######变量传入支持