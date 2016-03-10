# 最新加入组件制作
```html
<php>$last_users=sp_get_users("field:*;limit:0,8;order:create_time desc;");</php>
<ul class="list-unstyled tc-photos margin-bottom-30">
<foreach name="last_users" item="vo">
    <li>
        <a href="{:U('user/index/index',array('id'=>$vo['id']))}">
        <img alt="" src="{:U('user/public/avatar',array('id'=>$vo['id']))}">
        </a>
    </li>
</foreach>
</ul>
```
