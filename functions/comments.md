#Comments()

> V1.1.1新增

```php
Comments($table,$post_id,$params=array())
```
###### 功能:
生成评论组件

###### 参数:
`$table`:评论对象所在的表,不带表前缀   

`$post_id`:评论对象的id

`$params`:额外参数,类型为数组,目前只支持tpl参数


######模板中使用
```php
<!-- 评论文章表里的某个ID为$object_id的文章-->
{:Comments("posts",$object_id)}

<!-- 
    评论文章表里的某个ID为$object_id的文章,
    并且使用mycomments模板(此模板位于当前主题 Comment目录下)
-->
{:Comments("posts",$object_id,array('tpl'=>'mycomments'))}


```