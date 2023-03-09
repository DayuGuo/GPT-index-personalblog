#Permanent
[[Blog_MOC]] 

[Rime | 中州韵输入法引擎](https://rime.im/) 是一个跨平台的「输入法框架」，给予用户很高的权限，可根据自身使用习惯和场景设定。 [macOS版叫「鼠须管」](https://github.com/rime/squirrel) ，windows版叫「小狼毫」，名字都很有意思。
![[Pasted image 20220605221025.png]]
几年前在 windows 上有使用过一段时间 Rime，那时候我的需求还比较简单，对个性化的要求不高，也不懂代码，很快就弃用了。最近机缘巧合之下，再次启用了它，感觉非常好。
其优点主要有以下几条：
- 开源，免费
- 速度快，无广告
- 多平台可用
- SpellingAlgebra 技术
- 不依赖网络运行，重视隐私安全
- 高度个性化设置，重视用户体验
- Github 上有很多资源可用
- 自定义标点键位，并且可以一对多，符合我现在的输入习惯，推荐阅读 [Github 上的这份指南](https://github.com/sparanoid/chinese-copywriting-guidelines) 和 [W3C 的中文排版要求](https://w3c.github.io/clreq/)
- 快捷输入时间、日期、星期等
- macOS 自带的输入法太难用了
- 支持 icloud 备份
- 支持朙月拼音、小鹤双拼、自然码双拼，对繁体和小语种的支持好

另外，还有一些小细节做的很好，比如可以启用对特定应用的默认输入法切换。这部分我以前是用「[自动切换输入法](https://apps.apple.com/cn/app/%E8%87%AA%E5%8A%A8%E5%88%87%E6%8D%A2%E8%BE%93%E5%85%A5%E6%B3%95/id1470350547?mt=12)」或「[Input Source Pro](https://inputsource.pro/zh-CN)」实现的。切换中英文的时候，Rime 也默认会有提示，如下图。不过，Input Source Pro 所支持的根据不同网站切换输入法，Rime 似乎不能实现。
![[Pasted image 20220605220644.png]]

缺点也很明显，需要用户对代码有基础了解。上面提到的优点，很多也非刚需，其实可有可无。配置完成后，**除了小众用户外，对大部分用户的实际体验提升并不大**，各系统自带的输入法已经能很好满足需求。

# 即开即用的配置文件库
可以在官网下载安装，macOS 上也可通过 Homebrew 安装：
```
brew install --cask squirrel
```

分享两个很好用 Rime 配置库，即使没有编程经验，也能很快开始使用。

## Rime 鼠须管输入法傻瓜式配置指南
https://github.com/wongdean/rime-settings
这个库的特点外观方面复刻了 macOS 自带的输入法皮肤，自带了很丰富的主流词库，快捷输入也设置的很丰富。
最后更新日期：2021-04-05

## Rime 鼠须管（Squirrel）朙月拼音、小鹤双拼、自然码双拼配置详解（推荐）
https://github.com/ssnhd/rime
实际使用体验与上面一款相仿，选择它，是因为它的 [技术文档](https://ssnhd.com/2022/01/06/rime/) 写的特别详细，每个子文件的定位和用途都用思维导图标明了。初学者在通读这份文档后，就能非常全面的了解 Rime 和这份配置文件，并且具备了基础的配置能力。icloud 同步等技巧，我都是从这份文档中学习的。
最后更新日期：2022-05
![[Pasted image 20220605222638.png]]

