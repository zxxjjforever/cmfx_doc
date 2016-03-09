# sp_verifycode_img()

示例：
```php
<?php
$img=sp_verifycode_img();//不传入参数，全部使用默认值
echo $img;
$img=sp_verifycode_img('code_len=4&font_size=20&width=238','title="点击获取"'); //传入参数
echo $img;
?>
```


```html
<!--关于参数1:$param-->
<!--

-->


<php>

</php
<!--也可以-->
{:sp_verifycode_img()}

参数1：

$style ='code_len=4&font_size=15&width=100&height=35&charset=1234567890'；

code_len 字符长度

font_size 字体大小

width 生成图片宽度

heigh 生成图片高度

charset 要显示的字符集
```


> 注：此函数仅生成img标签，应该配合在表单加入name=verify的input标签