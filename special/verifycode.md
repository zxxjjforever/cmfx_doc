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

<!--你可以在任何一个需要验证码的表单里生成一个验证码,同时为它增加一个name为vefify 的 input-->
<input type="text" id="input_verify" name="verify"  placeholder="验证码" class="form-control">
```
######一个带验证码的表单
```php
<!--这是一个完整的ThinkCMF登录的表单-->
<h2 class="text-center">用户登录</h2>
<form class="form-horizontal js-ajax-forms" action="{:U('user/login/dologin')}" method="post">
	<div class="form-group">
		<input type="text" id="input_username" name="username" placeholder="手机号/邮箱/用户名" class="form-control">
	</div>

	<div class="form-group">
		<input type="password" id="input_password" name="password" placeholder="密码" class="form-control">
	</div>

	<div class="form-group">
		<div class="row">
			<div class="col-md-6">
				<input type="text" id="input_verify" name="verify"  placeholder="验证码" class="form-control">
			</div>
			<div class="col-md-6">
				{:sp_verifycode_img('length=4&font_size=14&width=100&height=34&charset=2345678&use_noise=1&use_curve=0')}
			</div>
		</div>
		
	</div>

	<div class="form-group">
		<input type="hidden" name="redirect" value="{:I('get.redirect','')}">
		<button class="btn btn-primary btn-block js-ajax-submit" type="submit" style="margin-left: 0px">确定</button>
	</div>

	<div class="form-group" style="text-align: center;">
		<ul class="list-inline">
			<li><a href="{:leuu('user/register/index')}">现在注册</a></li>
			<li><a href="{:U('user/login/forgot_password')}">忘记密码</a></li>
		</ul>
	</div>
</form>
```
####2.验证码验证

