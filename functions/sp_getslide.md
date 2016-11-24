# sp_getslide()
```php
sp_getslide($slide,$limit=5,$order = "listorder ASC")
```
######功能:
根据幻灯片标识获取所有幻灯片

######参数:
`$slide`:幻灯片标识,后台可以设置
`$limit`:最多显示几张幻灯片
`$order`:按什么字段(slide表的字段)排序

######返回
数组,符合条件的幻灯片列表

######示例：
```php
    $slides=sp_getslide('top_slide');    //top_slide是你在后台创建的幻灯片标识
    print_r($slides);       //打印出获取的结果
```


######模板中用法：
```php
<php>
    $slides=sp_getslide('top_slide');
    print_r($slides);
</php>
<foreach name="slides" item="vo">
    <!--{$vo.slide_id}幻灯片id-->
    <!--{$vo.slide_cid}幻灯片分类id,对应于slide_cat表里的cid-->
    <!--{$vo.slide_name}幻灯片名称-->
    <!--{$vo.slide_pic}幻灯片图片路径相对于upload文件夹/data/upload/-->
    <!--{$vo.slide_url}幻灯片链接地址-->
    <!--{$vo.slide_des}幻灯片描述-->
    <!--{$vo.slide_content}幻灯片内容-->
    <a href="{$vo.slide_url}" target="_blank" title="{$vo.slide_content}">
        <img src="/data/upload/{$vo.slide_pic}"/>
    </a>
</foreach>
```