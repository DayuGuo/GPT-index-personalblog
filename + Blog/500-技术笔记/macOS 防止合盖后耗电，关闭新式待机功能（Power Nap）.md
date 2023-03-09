## 前言
使用 macbook 快三年，一直有 2 点让我觉得很奇怪：a）合盖后，放到包里，机器偶尔会发热严重；b）合盖后，蓝牙链接并不会马上中断。并没有导致严重后果，就一直没有深究。
昨天，看了 Linus 的新视频后我明白了原因[^1]。这个视频吐槽了 windows 版本更新后的新特性 - 新式待机（Modern Standby），合盖之后的耗电问题非常严重。windows 端的解决方案比较复杂，且并非所有笔记本都适用。
macOS 上也是类似的原因，不过还好有通用的解决的方法：
- 打开设置（System settings）
- 进入电池设置界面
- 下滑到底部，点击「选项」（Options）
- 如下图所示将「Enable Power Nap」和「Wake for network access」关闭即可！

![[Pasted image 20221212010914.png]]


## Reference ：
[^1]: [微软这是在逼我买MacBook - Windows新式待机 linus谈科技_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Pv4y1d7Ms/?vd_source=018975cd7c234eb2ada5f19ae5df4568)