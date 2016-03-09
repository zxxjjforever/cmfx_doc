# 热门文章组件制作

热门文章

<php>$hot_articles=sp_sql_posts("cid:$portal_index_lastnews;field:post_title,post_excerpt,tid,smeta;order:post_hits desc;limit:5;"); </php>
<ul class="unstyled">
 <foreach name="hot_articles" item="vo">
  <php>$top=$key<3?"top3":"";</php>
  <li class="{$top}">
      <i>{$key+1}</i>
      <a title="{$vo.post_title}" href="{:leuu('article/index',array('id'=>$vo['tid']))}">{$vo.post_title}</a></li>
 </foreach>
</ul>
