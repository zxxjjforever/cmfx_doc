# hook()

> X1.4.0新增

```php
hook($hook,$param)
```
######功能：  
添加钩子

######参数：  
`$hook`:钩子名称  
`$param`:传入参数，默认为空数组

######返回：  
无

######模板使用：
```php
{:hook('footer')}
{:hook('sider',array('text'=>'hello ThinkCMF')}
```

######控制器方法里使用:
```php
//不带参数
hook('your_hook_name');

//带参数
hook('your_hook_name',array('text'=>'Hello ThinkCMF'));

```
