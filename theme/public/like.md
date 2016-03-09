# 点赞组件

点赞组件
```html
<a href="{:U('article/do_like',array('id'=>$object_id))}" class="js-count-btn"><i class="fa fa-thumbs-up"></i><span class="count">{$post_like}</span></a>
```

分解组件：
```html
<!-- 点赞链接 须传入文章id -->
href="{:U('article/do_like',array('id'=>$vo['object_id']))}"
```
js类名：

js-count-btn 
<!--
js数量操作组件，加上此类名的a标签为可以实现数量增加ajax操作；
ajax执行成功返回后对其内类名包含count的标签进行数量加1操作
-->


此组件可复用，只要链接是数量操作，开发者可以在自己的应用里添加相应操作