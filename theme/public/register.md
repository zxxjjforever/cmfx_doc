# 本站用户注册模板制作

模板文件：User/register.html

<form class="form-horizontal js-ajax-form" action="{:U('user/register/doregister')}" method="post">
    <label class="control-label" for="input_username">账号</label>
    <input type="text" id="input_username" name="username" placeholder="请输入账号" class="span3">
    
    <label class="control-label" for="input_email">邮箱</label>
    <input type="text" id="input_email" name="email" placeholder="请输入邮箱" class="span3">
    
    <label class="control-label" for="input_password">密码</label>
    <input type="password" id="input_password" name="password" placeholder="请输入密码" class="span3">
    
    <label class="control-label" for="input_repassword">重复密码</label>
    <input type="password" id="input_repassword" name="repassword" placeholder="请输入重复密码" class="span3">
    
    <label class="control-label" for="input_verify">验证码</label>
    <input type="text" id="input_verify" name="verify" placeholder="请输入验证码" class="span3">
    {:sp_verifycode_img('length=4&font_size=15&width=100&height=35&charset=1234567890')}
    
    <button class="btn btn-primary js-ajax-form" type="submit" data-wait="1500">确定注册</button>
</form>