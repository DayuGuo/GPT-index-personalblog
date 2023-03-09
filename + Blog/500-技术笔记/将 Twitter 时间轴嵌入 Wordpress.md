#Permanent
[[Blog_MOC]] 

# 需求
将 Twitter 时间轴嵌入 Wordpress。

# 解决方案
- 进入个人 Twitter 主页，复制链接地址。
![[Pasted image 20220524165322.png]]
- 进入 [Twitter Publish](https://publish.twitter.com/?buttonType=FollowButton&lang=en&maxheight=777) ，并在搜索框中黏贴。
![[Pasted image 20220524165452.png]]

- 有三种嵌入的形式，包括嵌入单个推文、嵌入时间轴和嵌入 Twitter 按钮。
![[Pasted image 20220524165610.png]]
- 这里我选择了「Embedded Timeline」，复制给出的 Code。
- 「Set customization options」中可以进行个性化设置，如默认语言和代码框大小。
![[Pasted image 20220524165712.png]]
- 随后进入 Wordpress 的编辑界面，添加「Custom HTML」，黏贴上面👆🏻得到的 Code，即可。点击 Preview 即可浏览实况，如不满意，可进行个性化设置。
![[Pasted image 20220524170030.png]]


除了 Twitter 官方的工具外，还有 [Tweetic](https://www.tweetic.io/)，可以把你的 Twitter 推文自动转换为静态 HTML。