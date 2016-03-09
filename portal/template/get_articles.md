# 获取文章的各种方式

sp_sql_posts()
示例：



<? php
$tag='cid:6;field:post_title,post_content;order:listorder asc';
$posts=sp_sql_posts($tag); 
print_r($posts);
$smeta=json_decode($vo['smeta'],true); //smeta处理方法，将其转化为数组
?>


$tag规则：

cid 分类id；

field 需要取出的内容，默认取出所有信息；order排序方式，可根据任何取出的字段排序，默认为按发布时间排序。



field可选参数：

term_id     文章分类id

post_author     文章作者id，后台管理员，对应于表users里的ID;

post_keywords     

post_date     文章发布日期 格式2014-01-01 00:00:00

post_content     文章内容

post_title     文章标题

post_excerpt     文章摘要

post_modified     文章更新日期 格式2014-01-01 00:00:00

smeta     文章扩展属性，以json格式保存，如属性thumb文章缩略图

user_nicename     管理员昵称

user_email     管理员邮箱



模板中用法：

<php>
$posts=sp_sql_posts('cid:6;field:post_title,post_content;order:listorder asc');
</php>

<foreach name="posts" item="vo">  /* 遍历数组 */
    {$vo.term_id }<br>
    {$vo.post_author }<br>
    {$vo.post_keywords }<br>
    {$vo.post_date }<br>
    {$vo.post_content }<br>
    {$vo.post_title }<br>
    {$vo.post_excerpt }<br>
    {$vo.post_modified}<br>
    {$vo.user_nicename }<br>
    {$vo.user_email }<br>
    <php>
    $smeta=json_decode($vo['smeta'],true);/* 把smeta转化成数组 */
    </php>
    <img src="{:sp_get_asset_upload_path($smeta['thumb'])}"/>
</foreach>


sp_sql_posts_paged()
示例：



<? php
$tag='cid:6;field:post_title,post_content;order:listorder asc';
$content=sp_sql_posts_paged($tag); 
$posts=$content['posts'];
$pager=$content['page'];
?>


$tag规则：

cid 分类id；

field 需要取出的内容，默认取出所有信息；order排序方式，可根据任何取出的字段排序，默认为按发布时间排序。



field可选参数：

term_id     文章分类id

post_author     文章作者id，后台管理员，对应于表users里的ID;

post_keywords     

post_date     文章发布日期 格式2014-01-01 00:00:00

post_content     文章内容

post_title     文章标题

post_excerpt     文章摘要

post_modified     文章更新日期 格式2014-01-01 00:00:00

smeta     文章扩展属性，以json格式保存，如属性thumb文章缩略图

user_nicename     管理员昵称

user_email     管理员邮箱



模板中用法：

<php>
$content=sp_sql_posts_paged('cid:6;field:post_title,post_content;order:listorder asc');
</php>

<foreach name="content['posts']" item="vo">  /* 遍历数组 */
    {$vo.term_id }<br>
    {$vo.post_author }<br>
    {$vo.post_keywords }<br>
    {$vo.post_date }<br>
    {$vo.post_content }<br>
    {$vo.post_title }<br>
    {$vo.post_excerpt }<br>
    {$vo.post_modified}<br>
    {$vo.user_nicename }<br>
    {$vo.user_email }<br>
    <php>
    $smeta=json_decode($vo['smeta'],true);/* 把smeta转化成数组 */
    </php>
    <img src="{:sp_get_asset_upload_path($smeta['thumb'])}"/>
</foreach>

<div>{$content.page}</div><!--分页-->