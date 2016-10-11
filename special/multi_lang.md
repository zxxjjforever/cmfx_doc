# 多语言开发

## 切换功能,需要自己先开启\application\Common\Conf\config.php

```
        'LANG_SWITCH_ON'        =>  true,   // 开启语言包功能
        'DEFAULT_LANG'          =>  'zh-cn', // 默认语言
        'LANG_LIST'             =>  'zh-cn,en-us,zh-tw',
        'LANG_AUTO_DETECT'      =>  true,   // 开启多语言查询，ture|false
```

默认语言为zh-cn，可用根据需要开发多个语言包,如后台设置模板为simplebootx，在themes目录下simplebootx目录为zh-cn语言模板，simplebootx_en-us为en-us语言模板，simplebootx_zh-tw对应的就是zh-tw语言包，simplebootx_mobile则为移动版模板，移动模板+"_language"则为移动版对应语言包，如simplebootx有三个语言版本，则对应目录为

```
simplebootx               // PC中文默认模板
simplebootx_en-us         // PC端zh-us语言模板
simplebootx_zh-tw         // PC端zh-tw语言模板
simplebootx_mobile        // 移动端中文默认模板
simplebootx_mobile_en-us  // 移动端en-us语言模板
simplebootx_mobile_zh-tw  // 移动端zh-tw语言模板
```

## 输出?l=en-us就可以打开语言切换

