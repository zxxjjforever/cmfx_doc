# sp_get_user_avatar_url()

> X2.2.0新增

```php
sp_get_user_avatar_url($avatar)
```

###### 功能：
获取用户头像地址

###### 参数：
`$avatar`: 数据库中保存的用户头像文件路径

###### 返回：
类型string,用户头像地址


###### 使用：
```php
$url = sp_get_user_avatar_url('avatart/2231rweqrqwer.png');
echo $url;//输出用户头像地址
```
