# sp_plugin_url()

> X1.4.0新增

```php
sp_plugin_url($url,$param,$domain)
```

功能：  
生成访问插件的url

参数：  
`$url`: url 格式：插件名://控制器名/方法  
`$param`:额外参数，默认为空数组  
`$domain`:是否添加域名，默认false

返回：
类型url

模板使用：
```php
{:sp_plugin_url('Demo://Index/index',array('id'=>2),true)}
{:sp_plugin_url('Demo://List/index',array('id'=>2))}
```
