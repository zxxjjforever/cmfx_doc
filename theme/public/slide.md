# 幻灯片制作

在后台扩展工具》幻灯片分类 添加分类标识为"portal\_index"的分类，然后在此分类添加幻灯片；
```html

cat_name：幻灯片类型名称
cat_idname：幻灯片标示
slide_name：幻灯片名称
slide_pic：幻灯片图片地址
slide_url：幻灯片URL
slide_des：幻灯片描述
slide_content：幻灯片内容


<php>
$home_slides=sp_getslide("portal_index");
</php>

<foreach name="home_slides" item="vo">
{$vo.slide_name}
<a href="{$vo.slide_url}">
    <img src="{:sp_get_asset_upload_path($vo['slide_pic'])}" alt="">
</a>
</foreach>
```

