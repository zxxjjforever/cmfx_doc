# sp_sql_page()

sp_sql_page($id)
功能：

获取指定id的页面

参数：

$id 页面的id

返回：

类型数组,符合条件的页面




示例：

<?php
$ID=1000;    //
$page=sp_sql_page($ID);
print_r($page);
