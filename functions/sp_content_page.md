# sp_content_page()

> X1.0新增

```php
sp_content_page($content,$pagetpl')
```
功能：  
对文本内容进行分页处理，返回当前页的内容，和分页html

参数：  
`$content`:要处理的文本内容；里面含有百度编辑器的分页标记;  
`$pagetpl`:分页模板；默认值{first}{prev}{list}{next}{last}



返回：  
类型数组

```php
array(
    "content"=>"",//当前页内容
    "page"=>""产生的分页html
);
```
