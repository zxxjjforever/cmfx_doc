# 验证码

#### 1.生成验证码

######生成验证码的函数:
```php
sp_verifycode_img($imgparam,$imgattrs);
```

######参数：  
`$imgparam`:控制验证码的样式,(默认值length=4&font_size=20&width=238&height=50&use_curve=1&use_noise=1)

`$imgattrs`:生成的验证码img标签的原生属性，除src,onclick之外都可以设置,(默认值:style="cursor: pointer;" title="点击获取")

######返回：
包括验证码的html代码

######模板里使用：

```php
<!--输出一个验证码-->
{:sp_verifycode_img('length=4&font_size=14&width=100&height=34&charset=2345678&use_noise=1&use_curve=0')}
<!--输出结果-->
<img class="verify_img" src="/index.php?g=api&m=checkcode&a=index&length=4&font_size=14&width=100&height=34&charset=2345678&use_noise=1&use_curve=0" onclick="this.src='/index.php?g=api&m=checkcode&a=index&length=4&font_size=14&width=100&height=34&charset=2345678&use_noise=1&use_curve=0&time='+Math.random();" style="cursor: pointer;" title="点击获取"/>

<!--把以上标签放在任何一个需要验证码的表单里,同时为它增加一个name为vefify 的 input-->
<input type="text" id="input_verify" name="verify"  placeholder="验证码" class="form-control">
```

######