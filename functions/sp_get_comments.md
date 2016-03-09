# sp_get_comments()

> X1.2新增

```php
sp_get_comments($tag,$where);
```
功能：

获取评论；



参数：

$tag:查询标签，默认：field:*;limit:0,5;order:createtime desc;

$where:查询where数组，按照thinkphp where array格式；



返回：

数组，评论