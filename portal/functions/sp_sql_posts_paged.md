# sp_sql_posts_paged()

```php
sp_sql_posts_paged($tag,$pagesize,$pagetpl)
```

功能：  
文章分页查询方法

参数：  
`$tag`:查询标签,以字符串方式传入,例："field:post_title,post_content;limit:0,8;order:post_date desc,listorder desc;where:id>0;"
```
field:调用post指定字段,如(id,post_title...) 默认全部
limit:数据条数,默认值为10,可以指定从第几条开始,如3,8(表示共调用8条,从第3条开始)
order:排序方式，如：post_date desc
where:查询条件，字符串形式，和sql语句一样
$pagesize:每页显示文章数
$pagetpl:分页模板，例："{first}{prev}{liststart}{list}{listend}{next}{last}"
```

返回：  
类型数组,带分页数据的文章列表

示例：
```php
<? php
$tag='cid:6;field:post_title,post_content;order:listorder asc';
$content=sp_sql_posts_paged($tag); 
$posts=$content['posts'];
$pager=$content['page'];
?>
```

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
```html
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
    <img src="/data/upload/{$smeta.thumb}"/>
</foreach>

<div>{$content.page}</div><!--分页-->
```