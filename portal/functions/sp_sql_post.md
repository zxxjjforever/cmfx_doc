# sp_sql_post()

示例：

<?php
$tid=1000;    //文章tid
$posts=sp_sql_post($tid,'field:post_title,post_content;');
print_r($posts);
//field 的可选参数已在sp_sql_posts()中说明
//smeta 处理方法已在sp_sql_posts()中说明 
?>
