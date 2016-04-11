# 忘记密码模板制作

模板文件：User/forgot_password.html
```html
<form class="form-horizontal js-ajax-form" action="{:U('user/login/doforgot_password')}" method="post">
    <label class="control-label" for="input_email">注册邮箱</label>
    <input type="email" id="input_email" name="email" class="span3">
    
    <label class="control-label" for="input_verify">验证码</label>
    <input type="text" id="input_verify" name="verify" class="span3">
    {:sp_verifycode_img('length=4&font_size=15&width=100&height=35&charset=1234567890')}
    <label class="control-label" for="input_repassword"></label>
    
    <button class="btn btn-primary js-ajax-form" type="submit">确定</button>
</form>
```