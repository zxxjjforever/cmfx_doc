#sp_get_asset_upload_path()
> V1.1.1新增

```php
<?php
$file='123adsfdsfads.png';//数据库保存的文件路径（都是相对于data/upload文件夹的）
$path=sp_get_asset_upload_path($file);//转化
echo $path;//输出可访问路径
?>
```
