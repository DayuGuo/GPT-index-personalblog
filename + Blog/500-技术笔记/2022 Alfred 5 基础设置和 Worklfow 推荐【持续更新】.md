[[Blog_MOC]] #Permanent

> 本文仅做笔记记录，更多信息请访问以下链接。主要参考资料：[分享一些 Alfred Workflows & Theme](https://sspai.com/post/69898) 【推荐】、[Mac 效率神器 Alfred 配置以及教程](https://www.bilibili.com/read/cv15495316) 和 [Alfred 上可提高工作效率的 Workflow 推荐](https://www.cnblogs.com/cangqinglang/p/15058274.html)。

# 背景
随着 Alfred 版本的更迭，很多 Workflow 都失效了，本文整理了 2022 年 6 月 Alfred 5 early access 版本更新后，能够正常使用的 Workflow。
本文中介绍的 Workflow 和 Theme 安装包被整理在：[https://github.com/DayuGuo/2022-Alfred-workflow-collection](https://github.com/DayuGuo/2022-Alfred-workflow-collection)，可直接下载安装。

# Theme
首先推荐 [Almost cloudy 主题](https://sspai.com/post/69898) ，简单舒适。
![[Pasted image 20220629153836.png]]
# 基础设置
- 在 General 中设置开机启动。
- Default Results 中 勾选 Floders、Documents 和 Images。
- Web Search 的 Keyword 可重新设置，比如 google 我设置成了 gg。另外，取消勾选不常用的，避免关键词冲突。
- Features 中的 Web Bookmarks 和 Clipboard History 是默认关闭的，这两个都很好用，可开启。
- Appearance 中点击 Options，即可查看高级设置，勾选 Hide hat on Alfred windows，能让界面更简洁。

# Workflow
可以在这个网站找合适的 Workflow：[https://www.packal.org/workflow-list](https://www.packal.org/workflow-list)

## 常用

- [EduicSearch](https://github.com/hanleylee/alfred-eudic-workflow) ，e + 单词，快速查询「当前已选择单词」或「搜索单词」。
- [经常打开的网页](https://00000520.xyz)，很推荐，设置了日常会查看的 2 个软件和 8 个网页，通过自定的快捷键打开。每天早上和睡前启动两次，浏览新闻和各类消息。
- [TinyPNG](https://github.com/alfredapp/tinypng-workflow)，具体教程见： [Alfred Workflow：通过 TinyPNG 快速压缩图片](https://anotherdayu.com/2022/3494/)
- [Recent Documents / Apps](https://github.com/mpco/AlfredWorkflow-Recent-Documents) ，ra 显示近期启动的App，rd 显示近期开启的文件。
- [Colors](https://www.packal.org/workflow/colors) ，根据输入的 RGB 值显示对应的 HSL 值。
- [Shortcuts](https://github.com/alfredapp/shortcuts-workflow/) ，启动已经安装的 macOS shortcuts。
- [关闭进程](https://github.com/nathangreenstein/alfred-process-killer) ，通过 kiil + 关键词，终止进程。
- [图片搜索](https://00000520.xyz) ，通过 ph +  关键词，同时在多个免费图片网站上检索。

## 可有可无
- [DOI Tools](https://github.com/hbuschme/doi-tools-alfred-workflow/) ，输入 DIO 即可自动转化为 BibTex，并储存在粘贴板中，LaTeX 用的多的话，很推荐。
- [Obsidian](https://github.com/hauselin/obsidian-alfred) ，可以做到基础的快捷搜索，但不是用 Obsidian 打开的。
- [Time conversion alfredworkflow](https://github.com/kangzhi2016/time-conversion-alfredworkflow)，基于 PHP 开发的 Workflow ，用于`时间戳`和`格式化时间`的相互转换。需要先安装 PHP 及关联框架，才能正常启动。
- [Hash](github.com/willfarrell) ，md5 + 关键词，快速生成md5值，按回车键可以复制到粘贴板。
- [Hidden files Toggle](https://github.com/logic1988/AlfredHiddenFilesToggle) ，显示默认隐藏的文件。
- [Battery](https://github.com/BenziAhamed/alfred-battery) ，显示更多电池信息，如循环次数、温度和电池建康状态。
- [HTTP](https://github.com/UpSync-Dev/alfred-http-status-codes)，查看各种报错代码的解释，如 404。
- [IP Address](https://github.com/alexchantastic/alfred-ip-address-workflow) ，查询本机 IP 地址。
- [New File](https://github.com/frankrausch/alfred-new-file) ，快速新建文件，不过好像只能新建 .txt。
- [wifi 切换](http://rodalgaard.dk/) ，快速切换和关闭wifi。
- [电影搜索](https://00000520.xyz) ，快速检索资源网站。
