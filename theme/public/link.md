# 友情链接制作
```html
<php>$links=sp_getlinks();</php>
<foreach name="links" item="vo">
    <a href="{$vo.link_url}" target="{$vo.link_target}">{$vo.link_name}</a>
</foreach>
```
