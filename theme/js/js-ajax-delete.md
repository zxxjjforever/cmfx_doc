# js-ajax-delete

ajax 删除组件
```html
<a href="你的删除url" class="js-ajax-delete" data-msg="确定删除它吗？">删除</a>
```

功能：

加上js-ajax-delete类名的a标签在单击后，会出现一个对话框，提示用户一些信息(信息内容为data-msg的属性值)，用户确定后会进行一个 ajax 请求，请求的 url为

href 属性的值，请求成功返回后，会刷新当前界面。

