# sp_get_image_url()


> X2.2.0新增
```php
sp_get_image_url($file,$style='')
```

###### 功能：
转化数据库保存图片的文件路径，为可以访问的url

###### 参数：
`$file`: 数据库中保存的文件名

`$style`:样式(七牛)


###### 返回：
类型string,图片可以访问的url


###### 使用：
```php
$url = sp_get_image_url('portal/23232.png');
```


