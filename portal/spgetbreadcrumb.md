# sp_get_breadcrumb()

> X2.2.0新增

```php
sp_get_breadcrumb($term_id)
```

###### 功能：
获取面包屑数据

###### 参数：
`$term_id`: 当前文章所在分类id,或者当前分类的id



###### 返回：

类型array,指定分类下的所有子分类



###### 使用：

```php

$terms = sp_get_all_child_terms(1);

```






