# sp_getcontent_imgs()

示例：

```php
<?php
$content='html格式内容';
$imgs=sp_getcontent_imgs($content);    //获取内容中图片信息
print_r($imginfo);
?>
```

返回字段说明：  
`title`:图片的title属性  
`alt`:图片的alt属性  
`src`:图片的资源路径