# 幻灯片制作

在后台扩展工具》幻灯片分类 添加分类标识为"portal_index"的分类，然后在此分类添加幻灯片；

<php>
$home_slides=sp_getslide("portal_index");
</php>

<foreach name="home_slides" item="vo">
{$vo.slide_name}
<a href="{$vo.slide_url}">
    <img src="{:sp_get_asset_upload_path($vo['slide_pic'])}" alt="">
</a>
</foreach>
