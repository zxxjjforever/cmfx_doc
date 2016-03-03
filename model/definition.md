# 模型定义

**为方便框架的后续升级，thinkcmf与thinkphp框架模型定义方法完全一致。**
***模型类并非必须定义，只有当存在独立的业务逻辑或者属性的时候才需要定义。***

模型类通常需要继承系统的\Think\Model类或其子类，下面是一个Home\Model\UserModel类的定义：
'''php
namespace Home\Model;
use Think\Model;
class UserModel extends Model {
}
'''

模型类的作用大多数情况是操作数据表的，如果按照系统的规范来命名模型类的话，大多数情况下是可以自动对应数据表。
模型类的命名规则是除去表前缀的数据表名称，采用驼峰法命名，并且首字母大写，然后加上模型层的名称（默认定义是Model），例如：
|模型名|	约定对应数据表（假设数据库的前缀定义是 cmf_）|
|--|--|
|UserModel|	cmf_user|
如果你的规则和上面的系统约定不符合，那么需要设置Model类的数据表名称属性，以确保能够找到对应的数据表。

1.数据表定义
在ThinkPHP的模型里面，有几个关于数据表名称的属性定义：

|属性	|说明|
|--|--|
|tablePrefix	|定义模型对应数据表的前缀，如果未定义则获取配置文件中的DB_PREFIX参数|
|tableName	|不包含表前缀的数据表名称，一般情况下默认和模型名称相同，只有当你的表名和当前的模型类的名称不同的时候才需要定义。|
|trueTableName	|包含前缀的数据表名称，也就是数据库中的实际表名，该名称无需设置，只有当上面的规则都不适用的情况或者特殊情况下才需要设置。|
|dbName	|定义模型当前对应的数据库名称，只有当你当前的模型类对应的数据库名称和配置文件不同的时候才需要定义。|
举个例子来加深理解，例如，在数据库里面有一个cmf_users表，而我们定义的模型类名称是UserModel，按照系统的约定，这个模型的名称是User，对应的数据表名称应该是cmf_user（全部小写），但是现在的数据表名称是cmf_users，因此我们就需要设置tableName属性来改变默认的规则（因为cmf程序默认已经在配置文件里面定义了DB_PREFIX 为 cmf_）。

'''php
namespace Home\Model;
use Think\Model;
class UserModel extends Model {
    protected $tableName = 'users';
}
'''

注意这个属性的定义不需要加表的前缀cmf_

如果我们需要CategoryModel模型对应操作的数据表是 top_user，那么我们只需要设置数据表前缀即可：

'''php

namespace Home\Model;
use Think\Model;
class UserModel extends Model {
    protected $tablePrefix = 'top_';
}
'''

如果你的数据表直接就是user，而没有前缀，则可以设置tablePrefix为空字符串。

'''php
namespace Home\Model;
use Think\Model;
class UserModel extends Model {
    protected $tablePrefix = '';
}
'''

没有表前缀的情况必须设置，否则会获取当前配置文件中的 DB_PREFIX。
而对于另外一种特殊情况，我们需要操作的数据表是top_categories，这个时候我们就需要定义 trueTableName 属性

'''php
namespace Home\Model;
use Think\Model;
class CategoryModel extends Model {
    protected $trueTableName = 'top_categories';
}
'''

注意trueTableName需要完整的表名定义。
除了数据表的定义外，还可以对数据库进行定义（用于操作当前数据库以外的数据表），例如 top.top_categories：

'''php
namespace Home\Model;
use Think\Model;
class CategoryModel extends Model {
    protected $trueTableName = 'top_categories';
    protected $dbName = 'top';
}
'''

系统的规则下，tableName会转换为小写定义，但是trueTableName定义的数据表名称是保持原样。因此，如果你的数据表名称需要区分大小写的情况，那么可以通过设置trueTableName定义来解决。

2.这里谈下THINKPHP的自动验证和自动完成功能（thinkcmf也是完全一样的）
假设上文我们已经定义了Home\Model\UserModel.class.php
代码完善后如下:

'''php
namespace Home\Model;
use Think\Model;
class UserModel extends Model {
  //自动完成
  protected $_auto = array (
           array('status','1'),  // 新增的时候把status字段设置为1
           array('random_str','creat_str',1,'function'), // 新增时自动完成random_str
       );
  //自动校验
  protected $_validate = array(
      array('verify','require','验证码必须！'), //默认情况下用正则进行验证
      array('name','','帐号名称已经存在！',0,'unique',1), // 在新增的时候验证name字段是否唯一
      array('value',array(1,2,3),'值的范围不正确！',2,'in'), // 当值不为空的时候判断是否在一个范围内
      array('name','check_name','密码格式不正确',0,'function'), // 自定义函数验证名称是否为admin
    );

  /*
  *为自动校验定义的校验方法 检测名称是否为admin
  *@prama $name 名字
  */
  function check_name($name){
      return $name=='admin'?false:true;
  }
  /*
  *为自动完成定义的完成方法//创建随机字符串用来
  *@prama $length 随机字符串长度
  */
  function creat_str($length=6){
      return sp_random_string($length);
  }
  /*
   // 随机字符串生成 cmf自带函数；
   // @param int $len 生成的字符串长度
   // @return string

  function sp_random_string($len = 6) {
  	$chars = array(
  			"a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k",
  			"l", "m", "n", "o", "p", "q", "r", "s", "t", "u", "v",
  			"w", "x", "y", "z", "A", "B", "C", "D", "E", "F", "G",
  			"H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R",
  			"S", "T", "U", "V", "W", "X", "Y", "Z", "0", "1", "2",
  			"3", "4", "5", "6", "7", "8", "9"
  	);
  	$charsLen = count($chars) - 1;
  	shuffle($chars);    // 将数组打乱
  	$output = "";
  	for ($i = 0; $i < $len; $i++) {
  		$output .= $chars[mt_rand(0, $charsLen)];
  	}
  	return $output;
  }
  */
}
'''


***参考文献***
1.http://www.kancloud.cn/manual/thinkphp/1728
2.http://www.thinkcmf.com/topic/topic/index/id/432.html
文档问题联系@iwzh
