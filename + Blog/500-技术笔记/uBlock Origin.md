AdGuard 是知名的网页广告屏蔽工具，用过多年，不过，从几年前改版开始，就臃肿了许多，且一直会有小问题：覆盖 Tampermonkey 的插件读取权限，和一些网络代理软件（Clash 和 surge）偶尔也会有冲突，并被 Clean my mac 列入 `Suspicious` 。
最近换电脑，顺便将网页广告屏蔽工具更换成了 [uBlock Origin](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm)。其优势是开源，占用的内存和 CPU 较低，仅需安装一个浏览器插件，比 Adguard 清爽了太多。
本来担心开源软件配置起来会比较麻烦，但 [cjx82630](https://github.com/cjx82630) 老师维护的清单让规则配置容易了许多。
- 浏览器可选择 Firefox 或 Chrome 
- 下载 [uBlock Origin Chrome 插件](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm)，Github： https://github.com/gorhill/uBlock ；
- 点击：[EasyList]( https://subscribe.adblockplus.org/?location=https://easylist-downloads.adblockplus.org/easylist.txt&title=EasyList "EasyList") ，然后右上角点击订阅；
- 点击：[EasyList China]( https://subscribe.adblockplus.org/?location=https://easylist-downloads.adblockplus.org/easylistchina.txt&title=EasyList%20China "EasyList China") ，然后右上角点击订阅；
- 点击：[EasyPrivacy]( https://subscribe.adblockplus.org/?location=https://easylist-downloads.adblockplus.org/easyprivacy.txt&title=EasyPrivacy "EasyPrivacy")，然后右上角点击订阅；
- 点击：[CJX's Annoyance List]( https://subscribe.adblockplus.org/?location=https://main.filter-delivery-staging.eyeo.com/v3/full/cjx-annoyance.txt&title=CJX "CJX's Annoyance List") ，然后右上角点击订阅。
启用的规则越多，占用的资源越多，所以选择目前需要的即可。这四套规则基本能满足我们的日常需要，如果发现链接订阅不了，请访问 https://github.com/cjx82630/cjxlist ，里面有一些镜像文件，国内可用。
如果有 Github 账户，可以给他加一个 Star。
![[CleanShot 2023-02-12 at 13.17.50@2x.png]]