# sp_get_image_preview_url()

> X2.2.0新增

```php
sp_get_image_preview_url($file,$style='watermark')
```

###### 功能：
获取图片预览链接

###### 参数：
`$file`: 数据库中保存的文件名
`$style`:样式(七牛)

###### 返回：
类型string,图片预览链接

###### 使用：
```php
$url = sp_get_image_preview_url('portal/23232.png');
```
