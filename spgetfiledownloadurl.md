# sp_get_file_download_url()

> X2.2.0新增

```php
sp_get_file_download_url($file,$expires=3600)
```

###### 功能：
获取文件下载链接

###### 参数：
`$file`: 数据库保存的文件路径

`$expires`:文件过期时间(七牛)

###### 返回：

类型string,文件下载链接

###### 使用：

```php
$url = sp_get_file_download_url('portal/23232.png');
```






