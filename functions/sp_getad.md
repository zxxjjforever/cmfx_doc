# sp_getad()
```php
 sp_getad();
```

######功能:
根据广告名称获取广告内容

######参数:
`$ad_name`:广告名称

######返回:
格式 string,广告内容

######示例：
```php
<?php
$ad_name='top_ad';
$ad_content=sp_getad('top_ad');    //获取广告内容
echo $ad_content; //输出广告内容
```

模板中用法：
```php
<div>
    {:sp_getad('top_ad')} <!--top_ad是后台设置的广告名称-->
</div>
```
