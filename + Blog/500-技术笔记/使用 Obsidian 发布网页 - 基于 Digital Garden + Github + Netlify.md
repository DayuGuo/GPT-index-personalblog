
 #Permanent
>本文翻译自 [Digital Garden 的官方文档](https://dg-docs.ole.dev/)。

# 引
Obsidian 的 [Publish](https://obsidian.md/publish) 服务非常昂贵，有一个 [Quickshare](https://github.com/mcndt/obsidian-quickshare) 插件能实现部分效果，但仅能分享单篇文章，并不理想。
近期找到了 [Digital Garden](https://github.com/oleeskild/obsidian-digital-garden) 插件，它的搭建过程和发布流程都清晰易懂，是理想的 Obsidian 建站工具。

# 入门
在 Obsidian 中，下载并启用社区插件 [Digital Garden](obsidian://show-plugin?id=digitalgarden) 。
准备 GitHub 帐户，如果您没有这个，请 [在​​此处](https://github.com/signup) 创建一个（如果访问 Github 有困难，请参考：[国内 Github 访问优化方案汇总（2022版） - Another Dayu](https://anotherdayu.com/2022/3413/)）。
准备 Netlify 账户，可使用 Github 账户[注册](https://app.netlify.com)。
打开这个库：[GitHub - oleeskild/digitalgarden](https://github.com/oleeskild/digitalgarden)，然后单击绿色的 “部署到 netlify” 按钮。这一步会打开 Netlify ，跟着提示进行操作，就可以在你的 Github 账户中创建这个库的副本，并将站点发布到互联网。
![[Pasted image 20221212100343.png]]
创建一个 GitHub 的访问令牌（Token），点击这个页面： [Token](https://github.com/settings/tokens/new?scopes=repo)。备注写一个便于记忆的，期限（Expiration）选无限期（no expiration）, 然后生成令牌即可。
跳转到下一个页面，复制生成好的令牌。
回到 Obsidian，点开 Digital Garden 的设置页面，填写 GitHub 库的名称、GitHub 用户名和 Token。
![[Pasted image 20221212103345.png]]
现在即可发布你的第一篇笔记。先在 Obsidian 中新建一个笔记，并将下面的代码添加到文件顶部。
```
---
dg-publish: true
dg-home: true
---
```
它应该看起来像这样：
![[Pasted image 20221212103513.png]]
 `dg-publish: true` 意味着你想将这个笔记发布到 Digital Garden ，没有加这条设置的笔记不会被发布。每条你想要发布到网络的 Obsidian 页面都需要加这条代码。
 `dg-home: true` 意味着你将这个页面设置为主页。
在 Windows/Linux 上按 CTRL+P（在 Mac 上按 CMD+P）打开命令面板，然后找到 「Digital Garden: Publish Single Note」命令。按回车。
回到 Netlify，可以看到发布的进度，显示 Published，即可查看网页。网页域名可以在 Netlify 中找到。
![[Pasted image 20221212103954.png]]
更多设置信息，可以查看官方文档： [Digital Garden Overview](https://dg-docs.ole.dev/)。

# 调整主题
调整主题也非常方便，在 Appearance Settings 中更改设置即可！