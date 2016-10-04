# sp_set_option()



> X2.2.0新增

```php
sp_set_option($key,$data)
```

###### 功能：
设置系统配置，通用

###### 参数：

`$key`: 配置的键名,英文下划线小写,最好加上自己的应用或插件名作为前级
`$data`:配置的值，数组

###### 返回：
类型boolean,true设置成功


###### 使用：

```php

$result = sp_set_option('portal_custom_settings',array('test'=>1));

```


