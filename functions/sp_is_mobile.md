# sp_is_mobile()

> 1.4.0新增

```php
sp_is_mobile()
```

######功能：  
判断是否为手机访问

######参数：  
无

######返回：  
boolean, true:是手机访问,false:不是

#####使用:
```php
    if(sp_is_mobile()){
        echo "我是手机用户呢!";
    }else{
        echo "我不是手机用户呀,那就是电脑用户呀!";
    }
```

######模板里使用
```php
    <if condition="sp_is_mobile()">
        <div>我是手机用户呢!</div>
    <else/>
        <div>我不是手机用户呀,那就是电脑用户呀!</div>
    </if>
```

