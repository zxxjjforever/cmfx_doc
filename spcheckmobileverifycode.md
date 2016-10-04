# sp\_check\_mobile\_verify\_code\(\)

> X2.3.0新增(暂时无法使用)

```php
 sp_check_mobile_verify_code($mobile='',$verifycode='') 
```

功能：
手机验证码检查，验证完后销毁验证码增加安全性

参数：
`$mobile`: 手机号
`$verifycode`:验证码
返回：
类型boolean
true：手机验证码正确，false：手机验证码错误

使用：
```php
$is_right_mobile_code = sp_check_mobile_verify_code('15121000000','123456');
```

