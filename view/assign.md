# 模板赋值
模板赋值就是在控制器里把控制器的变量传递给模板，对于系统变量你不用赋值我们可以通知特殊的标签在模板里输出,变量赋值我们都通过 assign 方法进行赋值；所有 assign方法，都必须在 display，show,fetch 方法执行前调用；



1.传递一个$name 到模板

```php
$this->assign('name','this is name');
```
这样就可以在模板使用$name 了，直接输出变量可以{$name}

也可以直接在 php 标签里使用这个变量；

```php
<php>
echo $name;
</php>
```
2.传递一个数组

```php
$user=array(
    'name'=>'Dean',
    'email'=>'cmf@simplewind.net',
    'phone'=>'15121010086'
);
$this->assign($user);
```
模板里就被传递了$name,$email,$phone 三个变量了，你可以直接输出{$name},{$email},{$phone}
