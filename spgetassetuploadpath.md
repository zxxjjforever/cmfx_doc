# sp_get_asset_upload_path()

> X1.6.0新增

```php
sp_get_asset_upload_path($file,$style='')
```

###### 功能：
转化数据库保存的文件路径，为可以访问的url

###### 参数：
`$file`: 数据库保存的文件路径
`$style`:样式(七牛)

###### 返回：
类型string,文件可以访问的url


###### 使用：
```php
$url = sp_get_asset_upload_path('portal/23232.png');
```


