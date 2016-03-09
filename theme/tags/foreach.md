# foreach

forech标签

属性  
`name`:表示数据源;  
`item`:表示循环变量;

```html
<foreach name="list" item="vo" > 
   {$vo.name} {$key}
</foreach>
```

更改属性key的变量名：
```html
<foreach name="list" item="vo" key="k"> 
   {$vo.name} {$k}
</foreach>
```
