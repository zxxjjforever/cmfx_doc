# 文章内页制作

可用变量
```
{$term_id 文章分类id，对应于表terms里的term_id;
{$post_author}<br><!-- 文章作者id，后台管理员，对应于表users里的ID;-->
{$post_keywords}<br><!---->
{$post_date}<br><!-- 文章发布日期 格式2014-01-01 00:00:00-->
{$post_content}<br><!-- 文章内容-->
{$post_title}<br><!-- 文章标题-->
{$post_excerpt}<br><!-- 文章摘要-->
{$post_modified}<br><!-- 文章更新日期 格式2014-01-01 00:00:00-->
{$smeta}<br><!-- 文章扩展属性，以json格式保存，如属性thumb文章缩略图，以后还会增加很多-->
{$user_nicename}<br><!-- 管理员昵称-->
{$user_email}<br><!-- 管理员邮箱-->
```

对变量smeta的转化
```html
<php>
  /*处理smeta*/
  $smeta=json_decode($smeta,true);/*把smeta转化成数组*/
</php>
{$smeta.thumb}<br><!-- thumb文章缩略图，以后还会增加很多-->

<img src="{:sp_get_asset_upload_path($smeta['thumb'])}"/>
```