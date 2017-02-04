# 七牛图片处理

七牛提供了强大的图片处理功能,ThinkCMF内部提供了七牛良好的支持,只要在后台"文件存储"里进行简单的设置就可以把全站的图片上传七牛了,前台使用七牛的强大api就可以对图片进行各种处理,如放大缩小,缩略图,加水印等.

ThinkCMF内部保存的文件路径是相对路径,假如你在七牛空间有个图片访问地址是`http://78re52.com1.z0.glb.clouddn.com/resource/gogopher.jpg`,那么你七牛空间的根目录就是`http://78re52.com1.z0.glb.clouddn.com/`,而在 CMF 的数据库里保存的是`resource/gogopher.jpg`,在前台模板你只要 sp_get_image_url()就可以获取到图片在七牛的访问地址了.具体用法如下:

```html
<img src="{:sp_get_image_url('resource/gogopher.jpg')}"/>
<!--这里输出的img地址就是http://78re52.com1.z0.glb.clouddn.com/resource/gogopher.jpg-->
```
![](http://78re52.com1.z0.glb.clouddn.com/resource/gogopher.jpg)

> 使用七牛的api生成图片300x300的缩略图

```html
<img src="http://78re52.com1.z0.glb.clouddn.com/resource/gogopher.jpg?imageView2/1/w/300/h/300" />
```

![](http://78re52.com1.z0.glb.clouddn.com/resource/gogopher.jpg?imageView2/1/w/300/h/300)

> 使用CMF标签生成七牛图片300x300的缩略图

```html
<img src="{:sp_get_image_url('resource/gogopher.jpg','?imageView2/1/w/300/h/300')}" />
```

![](http://78re52.com1.z0.glb.clouddn.com/resource/gogopher.jpg?imageView2/1/w/300/h/300)

所以图片处理的关键还是七牛的 api,ThinkCMF只是集成了七牛的用法,sp_get_image_url这个方法就是把数据库里存的相对图片路径转化为可以访问的路径;

```php
sp_get_image_url($file,$style)
```

##### 参数:

`$file`:数据库中保存的图片路径,是相对路径;

`$style`:图片显示样式,这个参数只在文件存储类型是七牛时才有用

在模板里显示一个400x300的图片缩略图
```html
<img src="{:sp_get_image_url('resource/gogopher.jpg','?imageView2/1/w/400/h/300')}" />
```

如果你想生成其它尺寸的图片,只要改变七牛 api 里的 `w`和`h`的大小就可以了!

这么牛的图片处理方式,只要把在cmf后台做一下设置就可以了,同时七牛也提供了免费的使用额度,对于流量小的企业站基本够用了,同时也保证了网站流畅性,ThinkCMF用户也可以享受ThinkCMF七牛专用优惠码,想再打个折就到[ThinkCMF官网首页](http://www.thinkcmf.com)找优惠码吧!

