# 文章相册制作

后台添加相册图集何如在视图显示
如：
打印$smeta查看数据结构
Array
(
    [thumb] => 
    [photo] => Array
        (
            [0] => Array
                (
                    [url] => 20160310/56e12de5d6f70.png
                    [alt] => QQ截图20160227144342
                )

            [1] => Array
                (
                    [url] => 20160310/56e12e2adbafc.png
                    [alt] => QQ截图20160227144342
                )

        )

)
此时遍历在视图遍历就能获得相册了
<foreach name="smeta['photo']" item="vo">
  <img src="{:sp_get_asset_upload_path($vo['url'])}" class="img-responsive img-thumbnail" alt="" />
</foreach>