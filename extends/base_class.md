# 几个重要基类

在ThinkCMFX系列版本的application/Common/Controller下有以下几个基类：

```
|-AppframeController     — ThinkCMF框架控件器基类，继承至Controller
  |-AdminbaseController   — ThinkCMF框架后台控件器基类，继承至AppframeController
  |-HomebaseController     — ThinkCMF框架前台控件器基类，继承至AppframeController
  |-MemberbaseController — ThinkCMF框架会员控件器基类，继承至HomebaseController
```

对于AdminbaseController和HomebaseController它们一个重要的方法display,分别用于管理后台和前台的模板显示，如果你的controller继承了AdminbaseController，在你调用display方法时，它会帮你去找admin/themes目录下的文件，同样HomebaseController也会帮你去找themes目录下的文件，这样就很好的实现了前后台模板的分离。

对于MemberbaseController，继承这个类的Controller会帮你判断会员的相关的操作，比如用户是否已经登陆，用户是否有权限访问此url。

所以想开发应用的同学，一定要在自己创建Controller之前想好你的Controller要完成什么功能，再去让它extends相应的基类。