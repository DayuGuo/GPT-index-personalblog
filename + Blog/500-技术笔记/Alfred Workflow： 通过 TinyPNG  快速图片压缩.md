[[Blog_MOC]] #Permanent

> 测试时间：2022 年 6 月 28 日
> 测试环境：macOS Monterey 12.4
> 测试结果：Alfred 4 和 [Alfred 5 early access](https://www.alfredapp.com/alfred-5-whats-new/)版 均可使用。14.5 mb 的 JPEG 文件，可以压缩到 1 mb。

# 背景
 [TinyPNG](https://tinypng.com/) 是一个图片压缩的网页服务，支持 WebP、PNG 和 JPEG，在减少存储大小的同时，没有明显的损失图像质量。
 [Alfred](https://www.alfredapp.com/) 是一款 macOS 上的效率软件，通过快捷键、关键词和插件提高工作效率。

先试了 4、5 个图片压缩 Alfred Workflow，都是很多年前的项目，已无法使用。最后在 Alfred 的[官方 Blog](https://www.alfredapp.com/blog/tips-and-tricks/tiny-png-workflow-compress-images/) 上，看到了 2022 年 1 月发布的 [TinyPNG Alfred workflow](https://github.com/alfredapp/tinypng-workflow) ，能够正常使用。
没有在中文平台上检索到这个 Workflow 的教程，便顺手翻译了。

# 操作流程
## 1. 申请 TinyPNG 的 API
进入 [TinyPNG Develop API](https://tinypng.com/developers) 界面，输入你的邮箱地址，点击 `Get your API key`，稍等片刻，即可收到邮件。
通过邮件链接，进入 `API Dashboard`，生成 `API Key`，并复制。每个月有 500 个免费的图象处理额度，普通用户完全够用了。
## 2. 安装 workflow
安装 Alfred。
然后，从 Github 上下载 [TinyPNG Alfred Workflow](https://github.com/alfredapp/tinypng-workflow#readme) ，可以得到一个`.alfredworkflow` 文件，双击它，即可弹出安装窗口。
在这里，不要直接点 `Import`，找到 `api_key` 那一栏，并将上一步中的 `API Key` 粘贴到下图中标红的位子，点击 `Import`，就完成安装了。

![[Pasted image 20220628154317.png]]
## 3. 使用
在 Alfred 中输入，`tinypng + 空格 + 图片名`，即可使用。
