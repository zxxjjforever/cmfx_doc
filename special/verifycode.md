# 验证码

#### 1.生成验证码
```php
sp_verifycode_img($imgparam,$imgattrs);
```

######参数：  
`$uid`: 当前登录用户或者管理员的id
`$name`:需要验证的规则列表,支持逗号分隔的权限规则或索引数组,默认为当前url  `$relation`:如果为 'or' 表示满足任一条规则即通过验证;如果为 'and'则表示需满足所有规则才能通过验证


######返回：
类型boolean通过验证返回true;失败返回false 使用：

```php
sp_auth_check(2);sp_auth_check(2,'admin/ad/index');sp_auth_check(2,array('admin/ad/index'));sp_auth_check(2,'admin/ad/index,admin/ad/add','and');

```
