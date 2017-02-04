# 包含文件

## tc_include

tc_include是前台模板包含文件的方法，用于替换原来的include的标签，实现更多功能

用法：

```html
<tc_include file="Public:nav"/> <!--加载的是当前模板的Public/nav.html-->
<tc_include file="Public/nav"/> <!--加载的是当前模板的Public/nav.html-->
<tc_include file="Portal/sidebar"/> <!--加载的是当前模板的Portal/sidebar.html-->
<tc_include file="User/Profile/nav"/> <!--加载的是当前模板的User/Profile/nav.html-->
```