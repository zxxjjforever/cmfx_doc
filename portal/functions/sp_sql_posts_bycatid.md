# sp_sql_posts_bycatid()

> X1.2新增
```php
sp_sql_posts_bycatid($cid,$tag,$where)
```

功能：  
根据分类文章分类ID 获取该分类下所有文章（包含子分类中文章），调用方式同sp_sql_posts

参数：  
`$cid`:分类id  
`$tag`:查询标签，以字符串方式传入,例："order:post_date desc,listorder desc;"field:调用post指定字段,如(id,post_title...) 默认全部
；limit:数据条数,默认值为10,可以指定从第几条开始,如3,8(表示共调用8条,从第3条开始);order:推荐方式(post_date) (desc/asc/rand())  
`$where`:按照thinkphp where array格式

返回：  
类型数组,符合条件的文章列表