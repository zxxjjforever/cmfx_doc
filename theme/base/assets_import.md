# 模板资源文件引入

引入css文件：
```html
<!-- 引入simpleboot库,此文件必须引入-->
<link href="__TMPL__Public/simpleboot/themes/simplebootx/theme.min.css" rel="stylesheet">

<!-- 引入simpleboot responsive库,此文件可选择引入，用于支持多屏幕响应-->
<link href="__TMPL__Public/simpleboot/bootstrap/css/bootstrap-responsive.min.css" rel="stylesheet">

<!-- 引入奥森图标库,此文件可选择引入，用于支持字体图标，用法见http://www.thinkcmf.com/font-->
<link href="__TMPL__Public/simpleboot/font-awesome/4.4.0/css/font-awesome.min.css"  rel="stylesheet" type="text/css">

<!-- 引入奥森图标ie7支持库,此文件可选择引入，用于支持IE7字体图标，用法见http://www.thinkcmf.com/font-->
<!--[if IE 7]>
 <link rel="stylesheet" href="__TMPL__Public/simpleboot/font-awesome/4.4.0/css/font-awesome-ie7.min.css">
<![endif]-->

<!-- 引入自定义css库，用户可加入自己的css组件-->
<link href="__TMPL__Public/css/style.css" rel="stylesheet">
```
以上内容加在</head>标签以前


引入js文件：
```html
<script type="text/javascript">
//全局变量,必须加入
var GV = {
    DIMAUB: "__ROOT__/",
    JS_ROOT: "public/js/"
};
</script>
<!-- 引入jquery-->
<script src="__PUBLIC__/js/jquery.js"></script>

<!-- 引入wind库，用于js异步加载-->
<script src="__PUBLIC__/js/wind.js"></script>

<!-- 引入bootstrap库，包含bootstrap各种组件-->
<script src="__TMPL__Public/simpleboot/bootstrap/js/bootstrap.min.js"></script>

<!-- 引入ThinkCMF前端库，包含ThinkCMF各种组件，方法，如评论，赞等-->
<script src="__PUBLIC__/js/frontend.js"></script>
```
以上内容加在</body>标签以前