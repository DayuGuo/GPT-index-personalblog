#Permanent
[[Blog_MOC]] 

## 网站简介

我的[第一个博客](https://gzy-dayu.cn/)使用 Hugo + Github + Netlify + 阿里云域名 + Blogdown + Utterances 搭建。除了阿里云域名需要少量付费，其他均为免费开源。

下图是 [1.9 版的个人博客](https://gzy-dayu.cn/)，功能已经很齐全了，简单轻便。1.0 版是用 Even 主题搭建的，可惜没有截图存档。

![[Pasted image 20221206200635.png]]
## 写在前面

本文没有很详细的教学，更多是分享我在学习过程中使用到的教程，并点出其中没有提到的要点。

## 准备工作

1.  注册 Github，并下载 Github Desktop。
2.  下载 R 和 Rstudio，熟悉其基础用法，使用常见 Package，如 ggplot2 和 dplyr 等。
3.  学习 Markdown 的基础语言，并了解什么是 Rmarkdown。在这个阶段推荐使用 Typora 软件实践。
4.  用 Rmarkdown（Rstudio的一个包）做一些简单的练习，并输出 pdf 或 html。

## Hugo 和 Blogdown

传统个人网站的实现需要学习 HTML、CSS 和 JavaScript，这对于一个非相关专业的业余 Blogger 来说负担有些大。而现在搭建个人网站已经变得越来越简单了，Github Page、Wordpress、Jekyll 和 Hugo 都是很不错的选择。其中 WordPress 的用户基数最大，有传言说白宫的部分网站也是用它搭建的，也是一个很不错的选择。如果你有个人云服务器，那选择和个性化就更高了。 本网站由 Hugo 框架的 Blogdown 搭建，是因为研究生阶段的师兄很推荐 Hugo。查阅相关资料后发现，这套系统已经很完善，且很好的**平衡了学习成本和个性化设置**。搭建这个网站的过程，其实也是一个学习 R 语言和个人网站相关语言的过程。对于一个非计算机专业的学生来说，这些东西还是挺有趣的，最后也挺有成就感的。

### Hugo 简介

Hugo 是由 Go 语言实现的静态网站生成器。简单、易用、高效、易扩展、快速部署。具体教程可见 [Hugo官方文档](https://gohugo.io/documentation/)和 [Hugo 中文文档](https://www.gohugo.org/)。不过传统的Hugo搭建是没有很多图形化界面，大多由命令行实现，其实对新手不是很友好。

### Blogdown

所以本网站使用的是基于Hugo核心的 [Blogdown](https://github.com/rstudio/blogdown)（R package）。这个包是谢益辉老师创建的，详细教程可见他的[《blogdown: Creating Websites with R Markdown》](https://bookdown.org/yihui/blogdown/)和[《用 blogdown 搭建一个静态网站》](https://www.bilibili.com/video/BV1ZK4y1s7ir)。

在这里特别推荐庄闪闪的 Blogdown 教学。微信公众号：`庄闪闪的 R 语言手册`，其中有一篇“手把手带你搭建个人博客（汇总版）”，写的相当好。能够让大家少走很多弯路。这份教程中，从用 Blogdown 的使用到上线 Netlify 都有涉及。

### 选择你喜欢的主题

入门的时候推荐默认的主题，或是 [hugo-theme-even](https://github.com/olOwOlo/hugo-theme-even), 其他主题见：[Hugo Themes](https://themes.gohugo.io/)。 在 `https://github.com/` 中，搜索关键词：`hugo theme`，或是使用搜索引擎，搜索：`hugo theme site:github.com`。都是不错的选择

本Blog使用的是 [Hugo-Book](https://github.com/alex-shpak/hugo-book)，是我比较喜欢的风格，且自带的插件比较多。

不过，需要注意的是，更换主题的成本还是比较大的，迁移前要做好重头再来的准备。 Yihui 是这样说的：

> Another thing to keep in mind is that the more effort you make in a complicated theme, the more difficult it is to switch to other themes in the future, because you may have customized a lot of things that are not straightforward to port to another theme.

### 其他需要注意的

对于非计算机专业的使用者，有一些底层逻辑只能在实践的过程中慢慢摸索。

1.  Blogdown 的核心在于 `config` 文件，它的后缀可以使 `.yaml` 也可以是 `.toml`，两种文件的语法不大一样，我推荐 `config.toml`。载入 themes 之后，可以发现在 `/themes` 里会多一个主题文件夹，里面有默认的配置文件（`config.toml`）如有误操作，可以去那里找一份。一般默认的配置文件中会对设置有很详细的标注。
2.  在`\layouts` 中有 partials 和 shortcodes 两个文件夹，分别代表了Hugo系统的两大插件形式。需要个性化设置的可以关注一下。
3.  [Hugo-book](https://hugo-book-demo.netlify.app/) 的示范网站里，有挺多 Shortcodes 模块的展示和教学，挺不错的。
4.  各文件夹的基础功能：

```
<pre class="wp-block-code">
├── config.toml     # 网站的配置信息
├── archetypes      # 存放 .md 文件的模板
├── content         # 存放 .md 文件
├── data            # 存放 Hugo 数据
├── layouts         # 存放布局文件,包括partials和shortcodes
├── public          # 公共文件夹，用于存放生成的站点文件
├── static          # 存放静态文件，比如图片、CSS、JS
└── themes          # 存放主题
```

## 阿里云域名

我大部分时间在国内，个人网址以后也可以有其他用途，就选了阿里云的域名。 以前的学习网站找不到了，大家可以参考这个：[github-netlify-阿里云配置](https://www.kancloud.cn/april_l/ssh-/968589)和 [Hugo + Github + 阿里云域名搭建个人博客（附 Netlify 部署方法）](https://taoziyu97.github.io/post/2021-1-11-build_blog/)。

## 评论区设置

这里介绍我使用过的两种。

### Disqus

教程可参考这一篇：[![This link targets a content farm](chrome-extension://lcghoajegeldpfkfaejegfobkapnemjl/img/content-farm-marker.svg "This link targets a content farm")博客 | hugo 博客添加 disqus评论系统](http://www.360doc.com/content/20/1016/11/9422167_940736984.shtml) 不过我使用下来，这套系统有一些问题。

-   需要翻墙使用
-   载入速度慢
-   需要基于 Disqus 网站使用

### Utterances

本网站的评论系统通过 [utteranc](https://utteranc.es/) 搭建。 utterances 是一款基于 Github Issue 的 Github 工具,优点主要是无广告、加载快、配置简单，轻量开源!

#### 操作步骤：

-   建一个新的 Github 库，名字可以叫 `Blogtalk` 之类的，这个库专门存放评论。
-   安装。utterances 是一款 Github app，安装很简单，在设置的时候选择 `Blogtalk`。
-   在 config 中添加：

```
<pre class="wp-block-code">
## 配置 utteranc评论,教程参考 https://utteranc.es/
[params.utteranc]
enable = false   
repo = DayuGuo/blogtalks-utterances ##换成自己得github库   
issueTerm = title   
theme = github-light 
```

-   更改 html 中的配置文件：

```
<pre class="wp-block-code">
{{ if .Site.Params.utteranc.enable }}
<script src=https://utteranc.es/client.js
repo={{ .Site.Params.utteranc.repo }}
issue-term={{ .Site.Params.utteranc.issueTerm }}
theme={{ .Site.Params.utteranc.theme }}
crossorigin=anonymous
async>
</script>
{{ end }}
```

-   在这个网站 `https://utteranc.es/` 配置。

```
<pre class="wp-block-code">
<script src=https://utteranc.es/client.js
        repo=DayuGuo/blogtalks-utterances
        issue-term=title
        theme=github-light
        crossorigin=anonymous
        async>
</script>
```
