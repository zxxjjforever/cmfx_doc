# 前台模板多语言

ThinkCMF前台模板多语言是使用多模板的方式来实现的,如:当前模板是`simplebootx`,如果想开启英文前台模板的话,就只要加一个模板名为 `simplebootx_en-us`模板就可以了;


### 前台模板多语言实现原理:

ThinkCMF在前台控制器加载模板文件时,会根据当前用户的浏览器语言或者用户指定的语言来加载模板文件,如果是中文用户就加载 simplebootx 里的模板文件,如果是英文用户就加载 simplebootx_en-us 里的模板文件;每个模板里数据调用是独立的,你可以在不同模板里做不同的配置,以调用不同的语言的内容;


### 为什么选用多模板形式实现前台多语言?

很多用户会疑问,这不是会增加维护的难度吗?为什么不用语言包的形式呢?

维护难度当然会增加,做一个模板和做两个模板是不一样的时间,但你想英文模板和中文模板无论从内容还风格都有可能会不同,一个模板,你要考虑很多布局上兼容的问题,同时,如果想对不同语言的用户做不同的体验上的界面设计,一个模板肯定无法满足,所以多模板形式才是前台多语言最好的选择,当然你在模板里也可以使用应用里设置的语言包.


### 多语言切换
只要在 url后带上`?l=语言包`,如`?l=en-us`,`?l=zh-cn`


### 例子

默认语言为zh-cn，可用根据需要开发多个语言包,如后台设置模板为simplebootx，在themes目录下simplebootx目录为zh-cn语言模板，simplebootx_en-us为en-us语言模板，simplebootx_zh-tw对应的就是zh-tw语言包，simplebootx_mobile则为移动版模板，移动模板+"_language"则为移动版对应语言包，如simplebootx有三个语言版本，则对应目录为 
y```
simplebootx // PC中文默认模板
simplebootx_en-us // PC端zh-us语言模板 
simplebootx_zh-tw // PC端zh-tw语言模板 
simplebootx_mobile // 移动端中文默认模板 
simplebootx_mobile_en-us // 移动端en-us语言模板 
simplebootx_mobile_zh-tw // 移动端zh-tw语言模板 
```

> 注:感谢[`@gai871013`](https://github.com/gai871013/cmfx_doc) 




