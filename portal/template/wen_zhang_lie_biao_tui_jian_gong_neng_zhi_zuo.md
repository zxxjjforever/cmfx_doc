# 文章列表推荐功能制作

在模版调用推荐功能：recommended，1推荐 0不推荐

我们在模板只要判断recommended等于1时给标题个样式变红就是推荐的文章
```html
<div class="span9">
  <div class="">
      <php>
          $lists = sp_sql_posts_paged("cid:$cat_id;order:istop desc , post_modified desc;",10);
      </php>
      <volist name="lists['posts']" id="vo">
      <php>
          $smeta=json_decode($vo['smeta'], true);
      </php>

      <div class="list-boxes">
          <h2><a href="{:leuu('article/index',array('id'=>$vo['tid'],'cid'=>$vo['term_id']))}" <if condition="$vo['recommended'] eq 1">style="color: red;" </if> >{$vo.post_title}</a></h2>
          <p>{$vo.post_excerpt|msubstr=0,256}</p>
          <div>
              <div class="pull-left">
                  <div class="list-actions">
                  <a href="javascript:;"><i class="fa fa-eye"></i><span>{$vo.post_hits}</span></a>
                  <a href="{:U('article/do_like',array('id'=>$vo['object_id']))}" class="js-count-btn"><i class="fa fa-thumbs-up"></i><span class="count">{$vo.post_like}</span></a>
                  <a href="{:U('user/favorite/do_favorite',array('id'=>$vo['object_id']))}" class="js-favorite-btn" data-title="{$vo.post_title}" data-url="{:U('portal/article/index',array('id'=>$vo['tid']))}" data-key="{:sp_get_favorite_key('posts',$vo['object_id'])}">
                      <i class="fa fa-star-o"></i>
                  </a>
                  </div>
              </div>
              <a class="btn btn-warning pull-right" href="{:leuu('article/index',array('id'=>$vo['tid'],'cid'=>$vo['term_id']))}">查看更多</a>
          </div>
      </div>
      </volist>

  </div>
  <div class="pagination"><ul>{$lists['page']}</ul></div>
</div>
```
