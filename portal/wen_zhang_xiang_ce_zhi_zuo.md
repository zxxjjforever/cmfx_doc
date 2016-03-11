# 文章相册制作

只

<foreach name="smeta['photo']" item="vo">
  <img src="{:sp_get_asset_upload_path($vo['url'])}" class="img-responsive img-thumbnail" alt="" />
</foreach>