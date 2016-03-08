# hook()

X1.4.0新增

hook($hook,$param)
功能：

在模板里添加钩子



参数：

$hook:钩子名称

$param:传入参数，默认为空数组



返回：

无

模板使用：

{:hook('footer')}

{:hook('sider',array('text'=>'hello ThinkCMF')}