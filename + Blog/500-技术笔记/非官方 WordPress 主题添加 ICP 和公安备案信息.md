#Permanent
[[Blog_MOC]] 
## 注册域名
本博客是在腾讯云上注册的域名，之前也在阿里云上购买过，个人感觉腾讯云的购买和后续控制台体验要稍好一些。如果网站面向的用户群体是国内的用户，推荐在国内平台购买域名，方便后续的备案。
国外的域名平台价格比国内这俩厂商便宜一些。这里推荐先使用 [TLD LIST](https://tld-list.com/) 进行比价，再决定从哪里购买域名。另外，如果想要在大平台消费，可以使用 [Google Domains](https://domains.google/) 和 [Domain.com](https://www.domain.com/?irclickid=Qsg274T-BxyIRV0xY5XmPXk9UkGXhUyDTVL4wk0&irgwc=1) ，他们提供的后续服务会好很多。

## 网站备案
需要备案的原因主要有两点：
1.  在国内，域名要备案了后，才能正常与公网 IP 地址链接。
2.  目前有的国内搜索引擎已经对没有做工信部 ICP 备案的网站不予收录。

### ICP 备案
注册完域名后，需要满 72 小时才能备案。所以最好尽早买域名，之后 3 天搭服务器，设置主题什么的就来的及。
腾讯云的备案流程很详细，跟着指引走就好。上海正常是 1-3 天内就能审批下来，我可能是由于疫情的缘故，审批了一周。
需要注意的是:
1.  申请好后会给你打一个电话，核验本人，并帮助修改一些网站简介。
2.  如果一审不过，后续会比较麻烦，所以资料要好好填写。
3.  这个阶段其实就可以开始操作「域名解析」和「安装 SSL 证书了」。
4.  按接线员的说法，备案成功后，会下发 ICP 备案号，之后 24 小时内需要登录公安部网站备案。

### 公安部备案
公安部的界面比 ICP 的要简陋很多。
1.  访问 [全国互联网安全管理服务平台](http://www.beian.gov.cn/) ，并在联网备案登录部分注册。
2.  填写开办者主体信息。
3.  单击新版网站申请，根据域名商和服务器商提供的信息填写。腾讯云提供了 [公安备案流程](https://cloud.tencent.com/document/product/243/19142) 。 需要注意的是，网站接入方式是选择「租赁虚拟空间」，这个我一开始没看教程填错了。
4.  之后就是定期查阅审批进度。
5. 同期，还需要关注「浦东网警」公众号，下载备案资料，并发送至邮箱 `pdtb@pudong.gov.cn` ，并提供测试账号和密码。

## 域名解析
我选择的是腾讯云自带的 DNSPod 解析套餐，这里有一个「坑」。DNSPod 的基础服务实际上是免费的，不过在操作流程中是默认选择了付费的套餐。个人感觉免费版就足够 Blog 网站的用户了。后续操作也是跟着指引就好，动线很清晰。完成后等待生效即可，一般半个小时左右即可。

Cloudflare 是用的比较多的一个国外的 NS 服务商，同时还提供 15 年的 SSL 证书以及免费 CDN，也可以防护 DDoS 攻击。也是使用免费的套餐就足够了。

## 安装 SSL 证书
这部分腾讯云也整理出了一个文档 - [如何安装 SSL 证书](https://cloud.tencent.com/document/product/1207/54869) 。这部分不得不表扬腾讯云，整套文档系统是基于 Github 和 Markdown 的，用户可以帮助迭代更新。使用 Linux 和宝塔面板搭建网站的朋友可以直接看 [宝塔面板 SSL 证书安装部署](https://cloud.tencent.com/document/product/400/50874) 。

## 添加备案信息
无论是网站工信部 ICP 备案还是网站公安备案，在备案通过后，要将相应的备案号按照相应的规定要求添加到网站的底栏，并添加链接。自此，才将网站备案全部完成。
这部分可以参考 辰鲲 Blog 的教程： [WordPress 网站添加 ICP 和公安备案信息](https://www.silenttwice.com/adding-website-filing-information-for-wordpress/) 。
需要在 Appearance - Theme File Editor - Theme Footer (footer.php)中添加以下代码：

```
<div>
<a>
<a href="<?php echo esc_url( __( 'http://beian.gov.cn', '' ) ); ?>">
 <?php printf( __('粤ICP备19111261号', '' ) ); ?>
</a>
</div>  
          
<div style="width:300px;margin:0 auto; padding:20px 0;"> <!-- 公安备案网址-->
<a target="_blank" href="https://beian.miit.gov.cn/" style="display:inline-block;text-decoration:none;height:20px;line-height:20px;"><img src="https://www.silenttwice.com/wp-content/uploads/2019/09/备案图标.png" style="float:left;"/><p style="float:left;height:20px;line-height:20px;margin: 0px 0px 0px 5px; color:#939393;">沪公网安备 31011502009490号</p></a>
</div>
```

上述方案的优点在于可以添加公安部的图标。

本网站选择了更简单的方式：
```
<p>Copyright © 2022 Dayu <br /><a href="http://beian.miit.gov.cn/" target="_blank" rel="external nofollow noopener">沪ICP备2022011392号</a> <span class="px-2">⋅</span> <a href="http://www.beian.gov.cn/portal/registerSystemInfo?recordcode=31011202013065" target="_blank" rel="external nofollow noopener">沪公网安备号</a></p>
```

