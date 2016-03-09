# sp_check_verify_code()

> X1.6.0新增

```php
sp_check_verify_code()
```

功能：  
验证码检查，验证完后销毁验证码增加安全性

参数：  
无

返回：  
类型boolean true|false;

使用：

```php
if(!sp_check_verify_code()){
    echo '验证码不正确';
}
```

> 注：表单提交时验证码name为verify；支持POST和GET方法