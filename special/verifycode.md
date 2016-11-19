# 验证码

#### 1.生成验证码

######生成验证码的函数:
```php
sp_verifycode_img($imgparam,$imgattrs);
```

######参数：  
`$imgparam`:控制验证码的样式,默认值length=4&font_size=20&width=238&height=50&use_curve=1&use_noise=1

`$imgattrs`:生成的验证码img标签的原生属性，除src,onclick之外都可以设置,默认值:[style="cursor: pointer;" title="点击获取"]

`$relation`:如果为 'or' 表示满足任一条规则即通过验证;如果为 'and'则表示需满足所有规则才能通过验证


######返回：
类型boolean通过验证返回true;失败返回false 使用：

```php
sp_auth_check(2);sp_auth_check(2,'admin/ad/index');sp_auth_check(2,array('admin/ad/index'));sp_auth_check(2,'admin/ad/index,admin/ad/add','and');

```
