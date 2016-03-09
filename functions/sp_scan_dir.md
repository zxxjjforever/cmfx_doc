# sp_scan_dir()

> X1.4.0新增

```php
sp_scan_dir($pattern,$flags)
```
功能：  
替代scan_dir的方法

参数：  
`$pattern`:检索模式 搜索模式 *.txt,*.doc; (同glog方法)  
`$flags`:返回模式 同glog方法

返回：  
类型数组

使用方法：

```php
//扫描application目录
$files=sp_scan_dir('application/*');//返回application目录下所有文件
```