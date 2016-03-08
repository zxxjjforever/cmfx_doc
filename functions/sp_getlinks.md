# sp_getlinks()
示例：

```php
<? php
    $links=sp_getlinks();        /*获取友情链接*/
    print_r($links);            /*打印出获取的结果*/
?>```
模板中用法：

```html
<php>
    $links=sp_getlinks();
</php>
<foreach name="links" item="vo">
    {$vo.link_name} <!--链接名称-->
    {$vo.link_url} <!--链接地址-->
    {$vo.link_target} <!--打开方式-->
    {$vo.link_description} <!--描述-->
    
    /*常见用法*/
    <a href="{$vo.link_url}" target="{$vo.link_target}">
        {$vo.link_name}
    </a>
</foreach>```
