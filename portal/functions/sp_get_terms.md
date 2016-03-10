# sp_get_terms()
```php
sp_get_terms($tag)
```
功能：  
返回符合条件的所有分类

参数：  
`$tag`:查询标签，以字符串方式传入,例："ids:1,2;field:term_id,name,description,seo_title;limit:0,8;order:path asc,listorder desc;where:term_id>0;"
```
ids:调用指定id的一个或多个数据,如 1,2,3
field:调用terms表里的指定字段,如(term_id,name...) 默认全部，用*代表全部
limit:数据条数,默认值为10,可以指定从第几条开始,如3,8(表示共调用8条,从第3条开始)
order:排序方式，如：path desc,listorder asc;
where:查询条件，字符串形式，和sql语句一样
```
返回：  
类型数组,符合条件的所有分类

示例：
```html
<php>
    $tag='ids:1,2;field:post_date,post_content;limit:10;order:post_date DESC;';
    /*
    $tag规则：ids分类id,以逗号隔开；field需要取出的内容，默认取出所有信息；order排序方式，可根据任何取出的字段排序，默认为按发布时间排序。
    $tag这是一个格式化的字符串，这种方式最大的好处就是方便日后扩展，它格式如《field+冒号+field支持的值，以英文逗号隔开+分号》
    */
    
    /*关于此函数的field:
    .它的可选值是：
   term_id 分类id
   name 分类名称
   taxonomy 分类的类型，用字符串表示，article表示文章
   description 分类描述
   parent 分类父级id,terms表中的term_id
   path 用于无限级分类的path,如0-1-29
   seo_title 
   seo_keywords 
   seo_description
   list_tpl 分类列表页的模板，对应于模板目录下Portal/文件名+.html，文件名默认为list
   one_tpl 分类单文章页的模板，对应于模板目录下Portal/文件名+.html，文件名默认为article
   listorder 分类排序
   status 分类状态0已回收，1正常
    */
    $terms=sp_get_terms($tag); 
</php>
<foreach name="terms" item="vo">
    
    {$vo.name }<br>
    {$vo.taxonomy }<br>
    {$vo.seo_title }<br>
    {$vo.seo_keywords }<br>
    {$vo.seo_description}<br>
    
</foreach>
```
