# sp_asset_relative_url()


> V1.1.1新增

```php
<?php
$file='/data/upload/1.png';//文件路径
$path=sp_get_asset_upload_path($file);//转化
echo $path;//输出数据库保存的文件路径（都是相对于data/upload文件夹的）,结果为1.png
```
