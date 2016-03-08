# sp_send_email()
X1.0新增

sp_send_email($address,$subject,$message)
功能：

发送邮件



参数：

$address:收件人地址

$subject:邮件主题

$message:邮件内容



返回：

类型数组，发送状态和信息

array(
    "error"=>"1",//有错误
    "message"=>""错误信息
);
array(
    "error"=>"0",//成功发送，无错误
);
