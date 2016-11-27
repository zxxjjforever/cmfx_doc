# 广告位制作

在文章底部加一个广告：

到后台扩展工具->网站广告->添加广告名称 为'portal_article_bottom'的广告，同时加上广告代码；

模板里代码如下：
```php
<div>
    {:sp_getad("portal_article_bottom")}
</div>
```