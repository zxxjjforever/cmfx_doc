# 连接数据库

一、全局配置定义
```php
return array(
    'DB_TYPE' => 'mysql',
    'DB_HOST' => '127.0.0.1',
    'DB_NAME' => 'thinkcmf',
    'DB_USER' => 'root',
    'DB_PWD' => 'root',
    'DB_PORT' => '3306',
    'DB_PREFIX' => 'cmf_',
    //密钥
    "AUTHCODE" => '2oF6v4m67BdQnfwMSf',
    //cookies
    "COOKIE_PREFIX" => '03a9uH_',
);
```
如果我们已经在配置文件中配置了额外的数据库连接信息，例如：

```php
return array(
    //数据库1
    'DB_TYPE' => 'mysql',
    'DB_HOST' => '127.0.0.1',
    'DB_NAME' => 'thinkcmf',
    'DB_USER' => 'root',
    'DB_PWD' => 'root',
    'DB_PORT' => '3306',
    'DB_PREFIX' => 'cmf_',
    //密钥
    "AUTHCODE" => '2oF6v4m67BdQnfwMSf',
    //cookies
    "COOKIE_PREFIX" => '03a9uH_',
    //数据库2
    'DB_CONFIG2' => array(
        'db_type'  => 'mysql',
        'db_user'  => 'root',
        'db_pwd'   => 'root',
        'db_host'  => '127.0.0.1',
        'db_port'  => '3306',
        'db_name'  => 'repast'
       ),
    );
```
二、实例化定义
```php
$User = M('User','cmf_','DB_CONFIG2'); 
```
                                                                                作者：小夏