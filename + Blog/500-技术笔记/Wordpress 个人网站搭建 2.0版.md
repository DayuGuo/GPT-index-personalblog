#Permanent
[[Blog_MOC]] 
## 引

一年前，用[Hugo内核和Github搭建](http://101.35.229.186/2022/60/ "Hugo内核和Github搭建")了我的[第一个个人网站](https://gzy-dayu.cn/ "第一个个人网站")，这是一个非常适合新手入门的搭配。不过后来因为一些原因，我开始尝试基于 VPS 和 WordPress 搭建个人博客。

![[Pasted image 20221206200521.png]]
截图于 2022 年 4 月 22 日

搭建个人博客需要三要素，即：

-   域名（Domain）：俗称网址，例如：www.anotherdayu.com。
-   虚拟主机(Hosting)：存放网站文件，数据的空间。选择稳定，速度快，美国ip。（海外主机免备案）
-   建站程序（Program）：WordPress，全球使用量最大的建站程序，功能十分强大。操作非常简单。

## 配置：

1.  腾讯云轻量应用服务器（210 RMB/三年），对于单纯搭建个人博客是够用了。
    -   服务器为上海，外网访问测试了一下 ping 稍高，但也蛮流畅的。
    -   2 核心
    -   内存 2 GB
    -   流量包 300 GB/月
    -   带宽 6 Mbps
    -   选的 Debian 11.1 框架
2.  域名（60左右/年）
3.  宝塔云国际服（Aapanel）
4.  WordPress
5.  主题用的 wordpress 内置的 Blocksy（免费版）

三年共花费：400 RMB左右，个人感觉还是挺划算的。

## 推荐教程

1.  [2021最新 腾讯云服务器安装宝塔面板建网站全过程（图文教程）](https://blog.csdn.net/longqizhanshen/article/details/107429411 "2021最新 腾讯云服务器安装宝塔面板建网站全过程（图文教程）")
2.  [2021年新版宝塔面板安装WordPress网站教程](https://blog.naibabiji.com/tutorial/bao-ta-an-zhuang-wordpress.html "2021年新版宝塔面板安装WordPress网站教程")
3.  [WordPress + VPS 建站教程](https://sspai.com/post/66447 "WordPress + VPS 建站教程")

上手不是很难，甚至某些地方比 Hugo 内核要好学很多，相关资料也比 Hugo 多一些。因为有[朋友](https://blog.jjjjjj.one/ "朋友")引导，没有走太多弯路，半天就基本搞定了，后面花了一些时间迁移资料，也都挺顺利的。

> Hugo 内核的网站基本不需要费用，而且因为是基于 Github，不用太担心删库和服务器的稳定性，很适合新手体验 Blog 搭建的过程。在搭建的时候，基本能把 R 语言的基础过一遍。

### 推荐的相关博客

1.  [主机百科](https://zhujiwiki.com/)
2.  `https://blog.laoda.de/`

### WordPress推荐插件

1.  WP Githuber MD，Markdown辅助插件
2.  Blocksy Companion，主题
3.  wordfence，防火墙
4.  [How to Use Revue Newsletter for Your WordPress Blog](https://www.wpsettingbox.com/revue-newsletter-tool-for-wordpress/ "How to Use Revue Newsletter for Your WordPress Blog")