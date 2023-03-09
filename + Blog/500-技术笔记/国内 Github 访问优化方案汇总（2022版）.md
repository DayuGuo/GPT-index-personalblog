#Permanent
[[Blog_MOC]] 

## 引
Github 上有大量开源资源供我们学习，但国内访问和下载困难的情况一直存在。很多人也没有稳定的科学上网手段，那么以下这些方法可以帮助你顺利访问 Github。
![[Pasted image 20220604131433.png]]
## 修改 Hosts（推荐）
这两个项目无需安装任何程序，通过修改本地 hosts 文件，试图解决：
- GitHub 访问速度慢的问题
- GitHub 项目中的图片显示不出的问题
开源仓库：
1.  [https://github.com/Licoy/fetch-github-hosts](https://github.com/Licoy/fetch-github-hosts)
2.  https://github.com/521xueweihan/GitHub520

比较基础的用法是复制以下内容到你电脑中的 Hosts 文件。
```
# GitHub520 Host Start
140.82.112.25                 alive.github.com
140.82.112.25                 live.github.com
185.199.108.154               github.githubassets.com
140.82.114.21                 central.github.com
185.199.108.133               desktop.githubusercontent.com
185.199.108.153               assets-cdn.github.com
185.199.108.133               camo.githubusercontent.com
185.199.108.133               github.map.fastly.net
199.232.69.194                github.global.ssl.fastly.net
140.82.112.4                  gist.github.com
185.199.108.153               github.io
140.82.114.3                  github.com
192.0.66.2                    github.blog
140.82.114.5                  api.github.com
185.199.108.133               raw.githubusercontent.com
185.199.108.133               user-images.githubusercontent.com
185.199.108.133               favicons.githubusercontent.com
185.199.108.133               avatars5.githubusercontent.com
185.199.108.133               avatars4.githubusercontent.com
185.199.108.133               avatars3.githubusercontent.com
185.199.108.133               avatars2.githubusercontent.com
185.199.108.133               avatars1.githubusercontent.com
185.199.108.133               avatars0.githubusercontent.com
185.199.108.133               avatars.githubusercontent.com
140.82.114.9                  codeload.github.com
54.231.200.129                github-cloud.s3.amazonaws.com
52.217.33.196                 github-com.s3.amazonaws.com
52.216.93.147                 github-production-release-asset-2e65be.s3.amazonaws.com
52.216.93.147                 github-production-user-asset-6210df.s3.amazonaws.com
52.217.207.33                 github-production-repository-file-5c1aeb.s3.amazonaws.com
185.199.108.153               githubstatus.com
64.71.144.211                 github.community
23.100.27.125                 github.dev
140.82.113.21                 collector.github.com
13.107.42.16                  pipelines.actions.githubusercontent.com
185.199.108.133               media.githubusercontent.com
185.199.108.133               cloud.githubusercontent.com
185.199.108.133               objects.githubusercontent.com

# Update time: 2022-06-04T12:05:45+08:00
# Update url: https://raw.hellogithub.com/hosts
# Star me: https://github.com/521xueweihan/GitHub520
# GitHub520 Host End
```

不过这个列表时会不断更新的，如果想要稳定更新 hosts，那么需要使用 [SwitchHosts](https://github.com/oldj/SwitchHosts) 软件（推荐）或 Adguard 软件（个人使用中存在一些 bug）。

## Ghrome 插件
- [Faster-hosts](https://github.com/gauseen/faster-hosts) （推荐），需要非官方渠道安装，下载完成之后解压缩包，在Chrome 地址栏输入`chrome://extensions/` 回车进入，勾选 `开发者模式`，选择 `加载已解压的扩展程序`， 选择刚才的解压目录即可。
- [Github 加速插件](https://chrome.google.com/webstore/detail/github%E5%8A%A0%E9%80%9F/ffjjnphohkfckeplcjflmgneebafggej?hl=zh-CN) ，需要在能正常打开 Github 的前提下使用。

## Github 镜像网站和 Tampermonkey 插件
2022 年 6 月 4 日可用 Github 镜像： https://hub.fastgit.xyz。缺点是这些镜像网站经常会失效。
也可以使用 Tampermonkey 插件：
- [FastGithub 镜像加速访问、克隆和下载](https://greasyfork.org/zh-CN/scripts/397419-fastgithub-%E9%95%9C%E5%83%8F%E5%8A%A0%E9%80%9F%E8%AE%BF%E9%97%AE-%E5%85%8B%E9%9A%86%E5%92%8C%E4%B8%8B%E8%BD%BD) ，快速跳转镜像网站。
- [Github 增强 - 高速下载](https://greasyfork.org/zh-CN/scripts/412245-github-%E5%A2%9E%E5%BC%BA-%E9%AB%98%E9%80%9F%E4%B8%8B%E8%BD%BD)

## Gitee 急速下载
Gitee 提供的著名开源项目镜像：https://gitee.com/mirrors，目前有 24788 个仓库。
- 缺点：库不全
![[Pasted image 20220604122637.png]]

## Github 下载加速网页版
Github 下载加速：http://toolwa.com/github/，使用方法：
1.  打开你要下载的 [GitHub](https://github.com/) 仓库页面
2.  点击右侧的绿色按钮 "Code" > "Download ZIP"
3.  等浏览器弹出下载框后复制下载框中的链接地址并粘贴到以上输入框
4.  点击加速下载

## 其他 Github 上的好用插件
- [Sourcegraph](https://chrome.google.com/webstore/detail/sourcegraph/dgjhfomjieaadpoljlnidmbgkdffpack)
- [Markdown Menu for GitHub](https://chrome.google.com/webstore/detail/markdown-menu-for-github/jekgocfoijmbgcjejohdgmojaejofdpo)
- GitHub Downloader
