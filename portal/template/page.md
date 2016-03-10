# 页面制作
可用变量
```
{$post_author}<br><!-- 页面作者id，后台管理员，对应于表users里的ID;-->
{$post_keywords}<br><!---->
{$post_date}<br><!-- 页面发布日期 格式2014-01-01 00:00:00-->
{$post_content}<br><!-- 页面内容-->
{$post_title}<br><!-- 页面标题-->
{$post_excerpt}<br><!-- 页面摘要-->
{$post_modified}<br><!-- 页面更新日期 格式2014-01-01 00:00:00-->
{$smeta}<br><!-- 页面扩展属性，以json格式保存，如属性thumb页面缩略图，以后还会增加很多-->
```

对变量smeta的转化
```html
<php>
/*处理smeta*/
$smeta=json_decode($smeta,true);/*把smeta转化成数组*/
</php>
{$smeta.thumb}<br><!-- thumb页面缩略图，以后还会增加很多-->

<img src="/data/upload/{$smeta.thumb}"/>
```
