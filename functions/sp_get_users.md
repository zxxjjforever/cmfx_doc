# sp_get_users()
> X1.2新增

```php
sp_get_users($tag,$where)
```

######功能：  
获取符合条件的用户列表；

######参数：  
`$tag`:查询标签，默认：field:\*;limit:0,8;order:create_time desc;  
`$where`:查询where数组，按照thinkphp where array格式；

######返回：  
数组，符合条件的用户列表


######使用
```php
    //获取最新注册的8个新用户
    $last8_users = sp_get_users('field:*;limit:0,8;order:create_time desc;');

    print_r($last8_users); // 打印用户列表
```


