# sp_get_users()
> X1.2新增

```php
sp_get_users($tag,$where)
```

功能：  
获取符合条件的用户；

参数：  
`$tag`:查询标签，默认：field:\*;limit:0,8;order:create_time desc;  
`$where`:查询where数组，按照thinkphp where array格式；

返回：  
数组，符合条件的用户
