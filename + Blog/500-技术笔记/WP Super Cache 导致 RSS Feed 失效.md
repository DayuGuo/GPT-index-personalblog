近期在[朋友](http://capturemoments.cn/)的反馈下，察觉到网站的 RSS Feed 失效了。
经排查，将原因锁定在 WP Super Cache 插件（即只要关闭这个插件，Feed 就能正常刷新）。
WP Super Cache 是一个很优秀的开源软件（免费），我并不想弃用它。
查阅相关资料，Boydo 的教程[^1]可行，在正常使用插件的情况下，恢复了 RSS Feed 的正常刷新，测试日期：2022-12-09。

# 步骤
1. 登陆 Wordpress 的后台管理界面
2. 在 Seeting 中找到 WP Super Cache 的设置界面
3. 点击 Advanced 选项卡
4. 下拉，找到「Accepted Filenames & Rejected URIs」
5. 勾选 Feeds (is_feed)
6. 点击保存

[^1]: https://mingersoft.com/blog/2012/08/wp-super-cache-and-rss/