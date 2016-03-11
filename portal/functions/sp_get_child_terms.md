# sp_get_child_terms()

```php
sp_get_child_terms($term_id)
```
功能：  
返回指定分类下的子分类

参数：  
`$term_id`:分类id

返回：  
类型数组,指定分类下的子分类

示例：
```php
<?php
 $term_id=1;
 $terms=sp_get_child_terms($term_id ); //获取子分类信息
 print_r($terms); //打印出子分类信息
?>
```
返回数组item说明：  
`term_id`:分类id  
`name`:分类名称  
`taxonomy`:分类的类型，用字符串表示，article表示文章  
`description`:分类描述  
`parent`:分类父级id,terms表中的term_id  
`seo_title`  
`seo_keywords`  
`seo_description`  
`list_tpl`:分类列表页的模板，对应于模板目录下Portal/文件名+.html，文件名默认为list  
`one_tpl`:     分类单文章页的模板，对应于模板目录下Portal/文件名+.html，文件名默认为article

模板中用法：
```php
<php>
    $term_id=1;
     $terms=sp_get_child_terms($term_id ); //获取子分类信息
</php>
<foreach name="terms" item="vo">
    {$vo.name}<!--打印出分类名称 -->
    
</foreach>
```