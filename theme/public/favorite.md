# 如何收藏

收藏组件，其它应用可以公用
```html
<a href="{:U('user/favorite/do_favorite')}" class="js-favorite-btn" data-title="收藏的内容标题" data-url="收藏的内容的url" data-key="{:sp_get_favorite_key('收藏内容所在表',收藏内容的id)}"></a>

<!--如文章收藏：-->
<a href="{:U('user/favorite/do_favorite',array('id'=>$object_id))}" class="js-favorite-btn" data-title="{$post_title}" data-url="{:U('article/index',array('id'=>$tid))}" data-key="{:sp_get_favorite_key('posts',$object_id)}">
 <i class="fa fa-star-o"></i></a>
```
```php
sp_get_favorite_key($table,$object_id)
```

参数1：收藏内容所在的表，不带表前缀的表名称，如cmf_posts应该改为“posts”;

参数2：收藏内容的id:


data-title:收藏的内容标题；

data-url:收藏内容的url；

data-key:安全key，用sp_get_favorite_key方法生成，防止有人提交错误数据；