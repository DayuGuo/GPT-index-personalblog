#Permanent | [[Blog_MOC]] | [[Wordpress]]

## 引
近期一直有两件事困扰我：
- 谷歌字体服务因网络问题在国内载入太慢。而本地字体因数据包大载入缓慢，即使是 lite 版依旧载入很慢；
- Wordpress 自带的 Gravatar 全球通用头像服务无法正常访问，尝试了一些在 `functions.php` 中添加代码的教程，效果依旧不理想（可能是跟插件或主题冲突）。
而 [WP-China-Yes](https://github.com/litepress/wp-china-yes) 这个插件，可以很方便的解决这两个问题。


## WP-China-Yes
该软件专为中国用户定制，集成了几个中国 wordpress 用户最紧迫的需求，且操作直接、低代码。
- 官方应用市场加速镜像；
- 将 Wordpress 依赖的静态文件，切换为公共资源，加速后台访问；
- 将 Gravatar 服务，替换为 Cravatar 服务；
- 加速谷歌字体；
- 加速谷歌前端公共库。
![[Pasted image 20221214100721.png]]

## 安装
前往 WP-China-Yes 的 [Github 库下载最新版](https://github.com/litepress/wp-china-yes/releases)，并在 wordpress 插件设置页面中本地上传安装即可。
最近更新日期：2022 年 11 月。

## LitePress
WP-China-Yes 插件是 [LitePress](https://litepress.cn/) 团队研发的，该团队致力于打造适合中国本土环境的 Wordpress 生态。
LitePress 还打造了一个 Wordpress 的中国发行版，并有一个[本土化翻译项目](https://litepress.cn/translate/)。
个人挺喜欢这个翻译项目的，界面简介易用，还提供机翻建议。以此为基础学英文也不错。
![[Pasted image 20221214101827.png]]

## 致谢
感谢中文博客圈微信群的群友和 [Jeff](https://www.yayu.net/) 提供了很多建议。