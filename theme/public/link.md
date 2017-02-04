# 友情链接制作
```php
sp_getlinks();
```
######功能:
获取所有友情连接

######参数:
无

######返回
数组,友情链接列表

######示例：
```php
$links=sp_getlinks();        /*获取友情链接*/
print_r($links);            /*打印出获取的结果*/
```

######模板中用法：
```php
<php>
    $links=sp_getlinks();
</php>
<foreach name="links" item="vo">
    {$vo.link_url} <!--链接地址-->
    {$vo.link_name} <!--链接名称-->
    {$vo.link_image} <!--链接图片,一般是网站logo图片地址-->
    {$vo.link_target} <!--打开方式-->
    {$vo.link_description} <!--描述-->
    
    /*常见用法*/
    <a href="{$vo.link_url}" target="{$vo.link_target}">
        <notempty name="vo.link_image">
				<img src="{:sp_get_image_url($vo['link_image'])}"><!-- 链接图片 -->
        </notempty>
        {$vo.link_name}
    </a>
</foreach>
```
