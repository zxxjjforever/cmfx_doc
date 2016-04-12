# 模板标签

作为内容管理框架，ThinkCMF允许app开发者自定义任意标签，ThinkCMF标签使用花括号作为定界符，如{$name}。

ThinkCMF系统内置的标签有：

`<php></php>`用来在模板中执行php的代码，示例代码：
```html
<php>echo "这个是在模板中执行的php程序"</php>
```
`<foreach></foreach>`遍历标签，示例代码：
```html
<php>$title=array("简介","产品","新闻");</php>        //遍历一个一维数组
<foreach name='title' item='vo'>
<div style="样式">
<a href="#">{$vo}</a>
</div>
</foreach>

<php>                     //遍历一个二维数组
$article = array
(
  "0"=>array
  (
  "title"=>"title1",
  "content"=>"content1",
  "date"=>"date1",
  ),
  "1"=>array
  (
  "title"=>"title2",
  "content"=>"content2",
  "date"=>"date2",
  )
);
</php>       
<foreach name='article' item='vo'>
<div style="样式">
<a href="#">{$vo.title}</a>
<p>{$vo.content}</p>
</div>
</foreach>
```
`<volist></volist>`按条件遍历，示例代码：
```html
<php>                     //遍历一个二维数组
$article = array
(
  "0"=>array
  (
  "title"=>"title1",
  "content"=>"content1",
  "date"=>"date1",
  ),
  "1"=>array
  (
  "title"=>"title2",
  "content"=>"content2",
  "date"=>"date2",
  )
);
</php>       
<volist name='article' id='vo'>
<div style="样式">
<a href="#">{$vo.title}</a>
<p>{$vo.content}</p>
</div>
</volist>
```
`<for></for>`循环标签，实例代码：
```html
<for start="开始值" end="结束值" name="循环变量名" >
 循环语句。。。
 </for>
 ```