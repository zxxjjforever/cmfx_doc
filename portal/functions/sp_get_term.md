# sp_get_term()
```php
sp_get_term($term_id)
```
功能：  
返回指定分类

参数：  
`$term_id`:分类id

返回：  
类型数组,符合条件的分类

示例：
```php
<?php
 $term_id=1;
 $term=sp_get_term($term_id ); //获取分类信息
 print_r($term); //打印出分类信息
?>
```
返回数组说明：

`term_id`:分类id   
`name`:分类名称  
`taxonomy`:分类的类型，用字符串表示，article表示文章  
`description`:      分类描述  
`parent`:分类父级id,terms表中的term_id  
`seo_title`  
`seo_keywords`  
`seo_description`  
`list_tpl`:分类列表页的模板，对应于模板目录下Portal/文件名+.html，文件名默认为list  
`one_tpl`:分类单文章页的模板，对应于模板目录下Portal/文件名+.html，文件名默认为article

