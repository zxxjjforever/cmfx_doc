# 添加留言控件

在模板中加入以下代码：

<form class="js-ajax-form" role="form" method="post" action="{:U('api/guestbook/addmsg')}">
    <label>姓名</label>
    <input type="text" class="span3" placeholder="Your name" name="full_name">
    <label>邮箱</label>
    <input type="email" class="span3" placeholder="Email address" name="email">
    <label>内容</label>
    <textarea class="span6" placeholder="Write message here..." name="msg"></textarea>
    <label>验证码</label>
    <input type="text" class="span3" placeholder="please enter the code" name="verify" autocomplete="off">
   {:sp_verifycode_img('length=4&font_size=20&width=238&height=34&font_color=&background=','style="cursor: pointer;vertical-align:top;" title="点击获取"')}
   <button type="submit" class="btn btn-primary js-ajax-submit">发送留言</button>
</form>
