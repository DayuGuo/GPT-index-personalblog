#Permanent
[[Blog_MOC]] 

## 本网站现使用的插件
1.  Blocksy companion
2.  Code Prettify
3.  Easy Table of Contents
4.  Wbox 时间轴文章归档
5.  Wordfence Security
6.  WP Statistics
7.  WP Super Cache

## Akismet Anti-Spam
需求：应对垃圾邮件骚扰
Used by millions, Akismet is quite possibly the best way in the world to **protect your blog from spam**. Your site is fully configured and being protected, even while you sleep.

## Blocksy Companion
需求：Blocksy 主题 的必装组件
本网站使用的网站主题是 Blocksy，这个插件提供了一些辅助功能。

## Code Prettify
需求：代码框的优化
Blocksy 本身的代码框设计的比较不合理，是简单的素色，程序员视角的阅读体验很糟糕，所以需要一些辅助插件帮助优化。
使用 [Enlighter](https://wordpress.org/plugins/enlighter/) 插件可以很好地实现这一点。不过，Blocksy 是基于谷腾堡编辑器实现的模块化编辑，Enlighter 只能在谷腾堡编辑界面实现，而我习惯于基于 Markdown 撰写 Blog。
所以这里选用了 [Code prettify](https://wordpress.org/plugins/code-prettify/) 作为代码框的优化软件，它最大的优点是自动化，安装激活后无需任何设置。效果如下，阅读体验还是不错的。
![[Pasted image 20220419163553.png]]

## Limit Login Attempts Reloaded
需求：IP 地址安全优化
这个软件可以限制每个 IP 地址的登录尝试次数。

## LuckyWP Table of Contents
需求：为 Posts 标准化的建立目录。
这个软件的强大之处在于，不仅能为 Posts 建立目录，还可以优化 Theme File Editor 的目录，效果如下：
![[Pasted image 20220419163842.png]]

## Post Views Counter
需求：显示博客页面访问记录
实际上这方面最好的插件是 [Site Kit by Google – Analytics, Search Console, AdSense, Speed](https://anotherdayu.com/wp-admin/plugin-install.php?tab=plugin-information&plugin=google-site-kit&TB_iframe=true&width=600&height=550) ，不过这个插件要使用谷歌服务，我的服务器不支持。故选择了这款 [Post Views Counter](https://wordpress.org/plugins/post-views-counter/) 。
 [WP Statistics](https://wordpress.org/plugins/wp-statistics/) 也是一个不错的选择！
效果如下：
![[Pasted image 20220419164110.png]]

## UpdraftPlus - Backup/Restore
需求：个人博客的备份
缺点：免费版是基于 Google Drive 备份的，而我的服务器在上海，所以并没能实际体验这个软件。

## Wbox 时间轴文章归档
需求：所有文字以时间轴排序，并对界面进行优化
详情见：`https://anotherdayu.com/timeline/`
![[Pasted image 20220419165209.png]]
## Wordfence Security
需求：个人网站防火墙
很经典的插件，几乎都会安装。

## WP Githuber MD
需求：在 Wordpress 中，使用 Markdown 编辑博客
很优秀的插件，但跟我使用的 Blocksy 主题冲突，有一些 bug，故近期没有使用。
现在采取的是先用 Markdown 写作软件（如 Typora 或 Obsidian）编辑文档，再拷贝到个人博客中。缺点是处理大量图片的时候很麻烦。

## WP Super Cache
需求：清除缓存

## WP-CDN-Yes
使用各大 CDN 厂商提供的 API 自动清理节点缓存，同时提供前台静态资源公共 CDN 加速。
此插件搭配静态缓存插件使用效果更佳。
