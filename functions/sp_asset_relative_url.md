# sp_asset_relative_url()


> V1.1.1新增

```php
sp_asset_relative_url($asset_url)
```

###### 功能:
获取文件相对路径

###### 参数:
`$asset_url`:文件URL

###### 返回
类型字符串,带协议的绝对地址直接返回原来的值,否则会转化为相对于系统upload 目录的文件路径

###### 实例
```php
<?php
$file='/data/upload/1.png';//文件路径
$path=sp_asset_relative_url($file);//转化
echo $path;//输出数据库保存的文件路径（都是相对于data/upload文件夹的）,结果为1.png
```
