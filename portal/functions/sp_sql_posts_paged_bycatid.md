#sp_sql_posts_paged_bycatid()

X1.2新增

sp_sql_posts_paged_bycatid($cid,$tag,$pagesize,$pagetpl)
功能：

根据分类文章分类ID 获取该分类下所有文章（包含子分类中文章），已经分页，调用方式同sp_sql_posts_paged



参数：

$cid:分类id

$tag:查询标签,以字符串方式传入,例："field:post_title,post_content;limit:0,8;order:post_date desc,listorder desc;where:id>0;"

    field:调用post指定字段,如(id,post_title...) 默认全部<br>

    limit:数据条数,默认值为10,可以指定从第几条开始,如3,8(表示共调用8条,从第3条开始)<br>

    order:排序方式，如：post_date desc<br>

    where:查询条件，字符串形式，和sql语句一样

$pagesize:每页显示文章数

$pagetpl:分页模板，例："{first}{prev}{liststart}{list}{listend}{next}{last}"



返回：

类型数组,符合条件的文章列表，及分页html

array(
    'content'=>'',//符合条件的文章列表
    'page'=>''//分页html
)
模板使用方法：

<div class="main-title">
	<php>
	    $result=sp_sql_posts_paged_bycatid($cat_id,"",20);
	</php>
</div>

<volist name="result['posts']" id="vo">
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
			<a href="{:U('article/do_like',array('id'=>$vo['object_id']))}" class="J_count_btn"><i class="fa fa-thumbs-up"></i><span class="count">{$vo.post_like}</span></a>
			<a href="{:U('user/favorite/do_favorite',array('id'=>$vo['object_id']))}" class="J_favorite_btn" data-title="{$vo.post_title}" data-url="{:U('portal/article/index',array('id'=>$vo['tid']))}" data-key="{:sp_get_favorite_key('posts',$vo['object_id'])}">
				<i class="fa fa-star-o"></i>
			</a>
			</div>
		</div>
		<a class="btn btn-warning pull-right" href="{:leuu('article/index',array('id'=>$vo['tid']))}">查看更多</a>
	</div>
</div>
</volist>

<div class="pagination">
	<ul>
		{$result['page']}
	</ul>
</div>

