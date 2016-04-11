# 模板结构
```
|--themes
    |--simplebootx                        //模板目录
        |--Comment
            |--comment.html           //评论模板，{:Comments()}中会调用
            |--index.html            //用户中心评论模板（链接:comment/comment/index）
        |--Portal
            |--404.html              //错误模板
            |--article.html          //默认文章页模板
            |--contact.html         //联系我们页面模板，可以后台页面编辑里更改，只需写文件名contact
            |--index.html           //首页模板
            |--list_masonry.html        //文章列表页瀑布流模板
            |--list.html               //文章列表页模板
            |--page.html           //默认页面模板
            |--product.html       //产品列表页模板，可以在后台分类编辑里设置列表页模板，只需写文件名product
            |--search.html           //文章搜索页模板
        |--Public                     //模板公共资源目录
        |--User
            |--Profile
                |--avatar.html  //头像编辑界面
                |--bang.html    //第三方账号绑定界面
                |--edit.html    //资料编辑界面
                |--password.html //密码修改界面
            |--active.html           //用户激活模板
            |--center.html        //用户中心模板
            |--disable.html          //用户未激活，重发激活邮件模板
            |--favorite.html      //我的收藏模板
            |--forgot_password.html //忘记密码模板
            |--index.html          //用户主页，公开主页
            |--login.html          //用户登录模板
            |--password_reset.html  //密码重置模板
            |--register.html        //用户注册模板
        |--config.html            //模板配置文件
        |--jump.html              //系统跳转页模板
        |--error.html               //系统action错误模板
        |--succes.html            //系统action操作成功模板
```