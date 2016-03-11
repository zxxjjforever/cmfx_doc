# 文章相册制作


<foreach name="smeta['photo']" item="vo">

                        <img src="{:sp_get_asset_upload_path($vo['url'])}" class="img-responsive img-thumbnail" alt="{$vo.post_title}" />
                    </foreach>