# sp\_compare\_password\(\)

> X2.1.0新增

```php
  sp_compare_password($password,$password_in_db)

```

功能：

CMF密码比较方法,所有涉及用户密码比较的地方都用这个方法

参数：

`$password`: 用户输入的密码

`$password_in_db`:数据库保存的经过加密后的密码串

返回：

类型boolean

密码相同，返回true

使用：

```php

$is_right = sp_compare_password('123456','###adfasfasdkfjaslkdjflksajerwqe');
```

