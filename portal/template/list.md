# 文章列表页制作
可用变量
```html
{$term_id}<br><!--分类id-->
{$cat_id}<br><!--分类id,同上-->
{$name}<br><!--分类名称-->
{$taxonomy}<br><!--分类的类型，用字符串表示，article表示文章-->
{$description}<br><!--分类描述-->
{$parent}<br><!--分类父级id,terms表中的term_id-->
{$seo_title}<br>
{$seo_keywords}<br>
{$seo_description}<br>
{$list_tpl}<br><!--分类列表页的模板，对应于模板目录下Portal/文件名+.html，文件名默认为list-->
{$one_tpl}<br><!--分类单文章页的模板，对应于模板目录下Portal/文件名+.html，文件名默认为article-->


<php>
    $lists = sp_sql_posts_paged("cid:$cat_id;order:post_date DESC;",10);
</php>
<volist name="lists['posts']" id="vo">
    <php>
	$smeta=json_decode($vo['smeta'], true);
    </php>
				
<div class="list-boxes">
    <h2><a href="{:leuu('article/index',array('id'=>$vo['tid']))}">{$vo.post_title}</a></h2>
    <p>{$vo.post_excerpt}</p>
    <div>
    <div class="pull-left">
        <div class="list-actions">
	<a href="javascript:;"><i class="fa fa-eye"></i><span>{$vo.post_hits}</span></a>
	<a href="{:U('article/do_like',array('id'=>$vo['object_id']))}" class="js-count-btn"><i class="fa fa-thumbs-up"></i><span class="count">{$vo.post_like}</span></a>
	<a href="{:U('user/favorite/do_favorite',array('id'=>$vo['object_id']))}" class="js-favorite-btn" data-title="{$vo.post_title}" data-url="{:U('portal/article/index',array('id'=>$vo['tid']))}" data-key="{:sp_get_favorite_key('posts',$vo['object_id'])}">i class="fa fa-star-o"></i></a>
    </div>
    </div>
    <a class="btn btn-warning pull-right" href="{:leuu('article/index',array('id'=>$vo['tid']))}">查看更多</a>
</div>
</div>
</volist>

<div class="pagination">
    <ul>
	{$lists['page']}
    </ul>
</div>			
```