#Permanent
[[Blog_MOC]] 

以下教程仅适用于 macOS，不包括 Windows 和 linux 下的教程。
# 变更国际服
在做以下操作前，最好先退出国服战网。
在 Finder 的应用程序中，找「战网 Battle.net」这个应用程序，右键菜单，显示包内容。contents/CodeSignature/，打开 CodeResources，弹出终端面板，输入以下内容：
```
/Applications/Battle.net.app/Contents/MacOS/Battle.net --setregion=US --setlanguage=enUS
```

需重新注册一个国际服的 [Battle.net](https://www.blizzard.com/zh-tw/) 的账号。
经测试，需要配置全局代理才能正常登录和游戏。
因网络原因，游戏体验略有影响，但可以接受，和欧洲的朋友一起玩不会很卡。

# 帧率优化
**想要游戏获得最佳体验，请全屏游戏，分辨率调到最低，并切换高帧率模式（这些都在游戏内的设置中）。**

1.  进入 Finder
2.  使用组合键 Shift+Command+G，输入 `~/Library/Preferences/Blizzard/Hearthstone/`
3.  或 `/Library/Preferences/Blizzard/Hearthstone/` 手动前往这个文件夹地址。
4.  找到 options.txt
5.  拉到最下方
6.  在 sound 或 soundvolume 的下一行加入 **targetframerate=60**

喜欢命令行的在终端下
`vim ~/Library/Preferences/Blizzard/Hearthstone/options.txt`

![[Pasted image 20220518154916.png]]
