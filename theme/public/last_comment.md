# 最新评论组件制作

<php>$last_comments=sp_get_comments("field:*;limit:0,5;order:createtime desc;");</php>
<foreach name="last_comments" item="vo">
    <div class="comment-ranking-inner">
    <i class="fa fa-comment"></i>
    <a href="{:U('user/index/index',array('id'=>$vo['uid']))}">{$vo.full_name}:</a>
    <span>{$vo.content}</span>
    <a href="__ROOT__/{$vo.url}#comment{$vo.id}">查看原文</a>
    <span class="comment-time">{:date('m月d日  H:i',strtotime($vo['createtime']))}
    </span>
    </div>
</foreach>