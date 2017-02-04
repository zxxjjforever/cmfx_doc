# 本站用户登录模板制作

模板文件：User/login.html
```html
<form class="js-ajax-form" action="{:U('user/login/dologin')}" method="post">
    <label for="input_username">账号</label>
    <input type="text" id="input_username" name="username" placeholder="请输入用户名或者邮箱" class="span3">
	
    <label for="input_password">密码</label>
    <input type="password" id="input_password" name="password" placeholder="请输入密码" class="span3">
    
    <label for="input_verify">验证码</label>
    <input type="text" id="input_verify" name="verify"  placeholder="请输入验证码" class="span3">
    {:sp_verifycode_img('length=4&font_size=15&width=100&height=35&charset=1234567890')}
	
    <button class="btn btn-primary js-ajax-submit" type="submit">确定</button>
</form>
```
