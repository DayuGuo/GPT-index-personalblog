#Permanent
[[Blog_MOC]] 

# 前言
[Flomo](https://flomoapp.com/) 是我很喜欢的子弹笔记软件，提供 API，可以和很多软件互动，如微信、微信读书、即刻和Notion等。
[NENO](<NENO https://github.com/openneno/neno>), 是一个仿 Flomo 的开源项目，可自建笔记软件（无需代码），通过 Github 储存，并在 Vercel 上部署。提供了utools、微信公众号、Telegram Bot、CLI、谷歌浏览器等外部扩展。
# 教程
注册 Github 帐号，打开链接：https://github.com/openneno/neno，点击下图中的「Deploy」
![[Pasted image 20221011174624.png]]
点击 Github 登陆帐号，再点击 GIT SCOPE 授权。
![[Pasted image 20221011174709.png]]
REPOSITORY NAME 可以随便取一个，如下图，我取的 abc。然后点击 Creat。
![[Pasted image 20221011174816.png]]
需要 1~2 分钟部署，部署成功后可以点击我画红圈的这部分，即可跳转网页。
![[Pasted image 20221011175029.png]]
跳转的这个网页即是以后的登陆界面，可储存在浏览器书签栏中（我的是：abc-mauve.vercel.app，每个人不同）。
点击下图中的设置键。
![[Pasted image 20221011175623.png]]
点击下图中圈起来的部分，可跳转到 Github 的 Token 设置页面。点击 Generate new token，Note 写 NENO，Expiration 勾选 No expiration。Select scopes 部分可以全勾选，然后点击 Creat new token。复制得到的新 Token。
![[Pasted image 20221011180209.png]]
假设我的 Token 为 `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`。如下图，填写信息，保存设置。
![[Pasted image 20221011180321.png]]
