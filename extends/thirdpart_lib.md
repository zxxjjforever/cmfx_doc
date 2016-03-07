# 引入第三方库

ThinkCMF第三方类库在simplewind/Core/Library/Vendor

如果你的第三方类库都放在Vendor目录下面，并且都以.php为类文件后缀，也没用采用命名空间的话，那么可以使用系统内置的vendor函数简化导入。例如，我们来导入二维码操作库phpqrcode,把 phpqrcode放到Vendor目录下面，这个时候phpqrcode主文件的路径就是 simplewind/Core/Library/Vendor/phpqrcode/phpqrcode.php，我们使用vendor 方法导入只需要使用：

```php
vendor('phpqrcode.phpqrcode');//导入类库
$QRcode = new \QRcode();//实例化，注意加\
```
这样就导入phpqrcode类库了，并完成了实例化

vendor方法也可以支持和import方法一样的基础路径和文件名后缀参数，例如：

```php
vendor('phpqrcode.phpqrcode','simplewind/Core/Library/Vendor','.php');
```
vendor方法：

vendor($class, $baseUrl, $ext)
功能：

快速导入第三方框架类库，所有第三方框架的类库文件统一放到系统的simplewind/Core/Library/Vendor目录下面

参数：

$class:类库,如phpqrcode.phpqrcode

$baseUrl:基础目录，默认simplewind/Core/Library/Vendor

$ext:类库后缀,默认为.php