# 获取内容

还有一种调用模板的情况是我们只想渲染后返回模板渲染后的数据而不是直接输出，这时我们会用 fetch方法；

fetch 的用法和 display 完全一样，只是不直接输出了；

```php
//不带任何参数
$content=$this->fetch();
```
此种方式系统会自动判断模板路径，并渲染出模板内容，此种方式模板路径是：主题名/应用名/控制器名/操作名+模板文件后缀名；

```php
$content=$this->fetch('edit');
```
此种方式表示调用此控制器下的 edit 操作的模板；

```php
$content=$this->fetch(':index');
```
此种方式表示调用此应用下 index 控制器的模板；



$str_content='this is a template file content,{$name}';
$content=$this->fetch('',$str_content);
此种方式是表示直接渲染传入的字符串里的模板内容；

通过以上方式得到渲染后的模板内容后，你可以对此内容做进一步处理；