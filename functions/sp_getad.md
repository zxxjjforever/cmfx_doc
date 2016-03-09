# sp_getad()

示例：
```php
<?php
$ad_name='top_ad';
$ad_content=sp_getad('top_ad');    //获取广告内容
echo $ad_content;
```

模板中用法：
```html
<div>
    {:sp_getad('top_ad')} <!--top_ad是后台设置的广告名称-->
</div>
```
