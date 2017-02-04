# sp_get_menu()

```php
sp_get_menu($id,$menu_root_ul_id,$filetpl,$foldertpl,$ul_class,$li_class,$menu_root_ul_class,$showlevel,$dropdown)
```

######功能:
生成指定ID的导航

######参数:
`$id`:导航id  
`$menu_root_ul_id`:菜单根节点ul标签的id属性值  
`$filetpl`:没有子菜单的菜单的html模板  
`$foldertpl`:有子菜单的菜单的html模板  
`$ul_class`:内部ul标签的class属性值  
`$li_class`:内部li标签的class属性值  
`$menu_root_ul_class`:菜单根节点ul标签的class属性值  
`$showlevel`:菜单根节点ul标签的class属性值
`$dropdown`:含有子菜单的li标签的class属性值,用于控制多级菜单的折叠


模板中用法：

```php
<php>
    $menu_root_ul_id="main-menu";
    $filetpl="<a href='\$href' target='\$target'>\$label</a>";
    $foldertpl="<a class='dropdown-toggle' href='\$href' target='\$target'>\$label</a>";
    $ul_class="dropdown-menu" ;/*内部ul标签的class属性值*/
    $li_class="" ;/*内部li标签的class属性值*/
    $menu_root_ul_class="nav";/*菜单根节点ul标签的class属性值*/
    $showlevel=6;/*显示菜单的层级*/
    $dropdown='dropdown';/*含有子菜单的li标签的class属性值,用于控制多级菜单的折叠*/
</php>

{:sp_get_menu("main",$menu_root_ul_id,$filetpl,$foldertpl,$ul_class,$li_class,$menu_root_ul_class,$showlevel,$dropdown)}
```

```php
<!--生成的代码如下：-->
<ul class="nav">
	<li class="active" id="menu-item-1"><a href="/" target="">首页</a></li>
	<li class="" id="menu-item-11"><a href="" target="">产品与服务</a></li>
	<li class="dropdown" id="menu-item-12">
	    <a class="dropdown-toggle" href="" target="">企业新闻</a>
            <ul class="dropdown-menu">
              <li class="" id="menu-item-11">
                  <a href="" target="">产品与服务</a>
              </li>
            </ul>
	</li>
</ul>
```
