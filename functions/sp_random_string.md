# sp_random_string()

<?php
$random=sp_random_string();//不指定位数，默认为6位
echo $random;
//或者
$random=sp_random_string(8);//指定返回8位随机字符串
echo $random;
?>