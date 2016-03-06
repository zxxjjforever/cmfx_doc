# 插件数据库模型
创建插件自定义模型
```php
namespace plugins\Demo\Model;//Demo插件英文名，改成你的插件英文就行了
use Common\Model\CommonModel;//继承CommonModel
class PluginDemoModel extends CommonModel{ //Demo插件英文名，改成你的插件英文就行了,插件数据表最好加个plugin前缀再加表名,这个类就是对应“表前缀+plugin_demo”表
	
	//自动验证
	protected $_validate = array(
			//array(验证字段,验证规则,错误提示,验证条件,附加规则,验证时间)
			//array('ad_name', 'require', '广告名称不能为空！', 1, 'regex', 3),
	);
	
	protected function _before_write(&$data) {
		parent::_before_write($data);
	}
	
	//自定义方法
	function test(){
		echo "hello";
	}
}
```


实例化模型：
```php
$plugin_demo_model=D("plugins://Demo/PluginDemo");//实例化自定义模型PluginDemo
$plugin_demo_model->test();//调用自定义模型PluginDemo里的test方法
		
$users_model=D("Users");//实例化Common模块下的Users模型
//$users_model=D("Common/Users");//也可以这样实例化Common模块下的Users模型
$users=$users_model->limit(0,5)->select();
		
print_r($users);```