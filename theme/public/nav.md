# 菜单导航制作

bootstrap导航：
```php
<?php
/*生成菜单的 id*/
$effected_id="main-nav";

/*无子菜单导航的模板*/
$filetpl="<a href='\$href' target='\$target'>\$label</a>";

/*有子菜单导航的模板*/
$foldertpl="<a href='\$href' target='\$target' class='dropdown-toggle' data-toggle='dropdown'>\$label <b class='caret'></b></a>";

/*有子菜单导航元素li的class属性*/
$dropdown='dropdown';

/*有子菜单导航元素ul的class属性*/
$ul_class="dropdown-menu";

/*菜单元素li的class属性/
$li_class="" ;

/*生成菜单的class属性*/
$style="nav";

/*显示的菜单层级*/
$showlevel=6;

echo sp_get_menu("main",$effected_id,$filetpl,$foldertpl,$ul_class,$li_class,$style,$showlevel,$dropdown);
?>
```