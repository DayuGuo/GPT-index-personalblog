Youtube Channel 自从支持自定义域名后，很难获取频道的「唯一 ID」，对 RSS 订阅和爬虫很不友好。
本文推荐三种获取 Youtube Channel 唯一 ID 的方案。
# 网页转换
这是最简单的一个方法。
- 复制频道主页的链接后， `https://www.youtube.com/@TchLiyongle`；
- 打开这个网站： https://commentpicker.com/youtube-channel-id.php ；
- 将频道主页的链接，粘贴到网站中。

![[Pasted image 20230110155403.png]]
- 红圈标注的部分，就是 Channel ID。
![[Pasted image 20230110155427.png]]

# Page Source 中查找
- 复制频道主页的链接后， `https://www.youtube.com/@TchLiyongle`；
- 在网页空白处，点击鼠标右键唤出菜单，点击「View Page Source」；
- 唤出搜索栏，搜索：`https://www.youtube.com/channel/`；
- 红圈标注处就是 Channel ID：`UCSs4A6HYKmHA2MG_0z-F0xw`。
![[Pasted image 20230111225511.png]]
# Developer Tools 中查找
- 打开你感兴趣的 Youtube 频道主页；
- 打开 Developer Tools，
	- Windows/Linux 上是 `F12` 快捷键，
	- macOS 上是 `option + ⌘ + J`；
- 选择「Elements」选项卡；
- 唤出搜索栏，搜索 `https://www.youtube.com/channel/`；
- 蓝圈处，即是 Channel id。
![[Pasted image 20230111230307.png]]

# Reference
https://mixedanalytics.com/blog/find-a-youtube-channel-id/