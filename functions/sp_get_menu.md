# sp_get_menu()
模板中用法：

```html
<php>
    $effected_id="menu-header";
    $filetpl="<a href='\$href' target='\$target'>\$label</a>";
    $foldertpl="<a class='dropdown-toggle' href='\$href' target='\$target'>\$label</a>";
    $ul_class="dropdown-menu" ;/*内部ul标签的class属性值*/
    $li_class="" ;/*内部li标签的class属性值*/
    $style="nav";/*最外层ul标签的class属性值*/
    $showlevel=6;/*显示的层级*/
    $dropdown='dropdown';/*含有子目录的li标签的class属性值*/
</php>

{:sp_get_menu("main",$effected_id,$filetpl,$foldertpl,$ul_class,$li_class,$style,$showlevel,$dropdown)}
```

```html
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
