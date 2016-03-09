# sp_check_user_action()

> X1.1新增

```php
sp_check_user_action($object,$count_limit,$ip_limit,$expire)
```
功能：  
检查用户对某个url,内容的可访问性，用于记录如是否赞过，是否访问过等等;开发者可以自由控制，对于没有必要做的检查可以不做，以减少服务器压力

参数说明：  
`$object`: 访问对象的id,格式：不带前缀的表名+id;如posts1表示xx_posts表里id为1的记录;如果object为空，表示只检查对某个url访问的合法性  
`$count_limit`: 访问次数限制,如1，表示只能访问一次  
`$ip_limit`: ip限制,false为不限制，true为限制  
`$expire`: 距离上次访问的最小时间单位s，0表示不限制，大于0表示最后访问$expire秒后才可以访问

返回：  
`true` 可访问，`false`不可访问