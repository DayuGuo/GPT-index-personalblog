# 引
豆瓣是一个出色的图书标注平台，但其缺点同样突出。
- 外文书收录的少；
- 因不可抗力，很多内容有被下架的风险；
- 越来越封闭。
最近我试图寻找一个合适的替代品，需求如下：
- 免费；
- 尽可能是去中心化和开源的；
- 低代码，学习成本低；
- 社区有活力；
- 数据可下载。

# 备选
【中文】
[Anobii]( https://www.anobii.com/zh-Hans )，繁体书较多，简体书较少，英文数据库不如 Goodreads。
【英文】
[Goodreads](https://www.goodreads.com/)  、[StoryGraph](https://www.thestorygraph.com/) 和 [Google Book](https://books.google.com/) 是外文数据库信息最全的，但对中文书的支持不够完整。
[Bookwyrm](https://bookwyrm.social/)，可翻译为书蛊，基于 mastodon，站点为 bookwyrm.social。开源，Github 有 1.4k 标记，社群比 NeoDB 有活力。可导入主流外国社群的资料。也是对中文书籍的支持不足，有一个很小的[中文社群](https://bookwyrm.social/group/3/s/)在慢慢维护，是一个很有潜力的图书社群。
【综合】
Notion 类的数据库软件，需要一定的学习和整理成本。豆瓣资料的迁移可参考：[教程](https://zhuzi.dev/2021/06/05/douban-backup-sync-notion/) 和 [豆瓣跑路计划](https://www.notion.so/952c54f01d3d462b804e194ebc1f4a9d)。
[Libib](https://www.libib.com/) ，支持中文书扫描，功能完整强大，但需要付费体验完整功能。
[NeoDB](https://neodb.social/)，同时支持豆瓣、Goodreads 和 Google Book，通过 Mastodon 登陆，界面友好。

# 我的选择：NeoDB
> NeoDB 致力于为联邦宇宙居民提供一个自由开放互联的书籍、电影、音乐和游戏收藏评论空间。

NeoDB 通过 [Mastodon](https://mastodon.social/) 登陆。
>Mastodon 是一个自由开源的去中心化的分布式微博客社交网络。
>Wiki

类似于 Twitter，不同之处是 Mastodon 由很多社区（服务器）构成，需要先选择一个合适的社群。
长毛象官方列表 ( https://joinmastodon.org/servers ) 中，可以根据 Topic 选择合适的社区。
随后，按指引注册即可。
个人主页中，`@anotherdayu@mastodon.social` 是你的个人 ID。
使用这个 ID 就能注册 NeoDB 了。
![[Pasted image 20230109230002.png]]

登陆后的使用和操作与豆瓣相似，功能都很基础，就不过多介绍了。
NeoDB 支持豆瓣， Goodreads， The Movie Database， Steam， Spotify， IMDB， Bangumi， Bandcamp 数据导入。
NeoDB 可通过[豆坟](https://blog.doufen.org/)从豆瓣迁移，使用指南： https://about.neodb.social/doc/howto/ 。

NeoDB 的优点：
- 免费；
- 支持多个数据库，对中英文内容都支持的很好；
- Mastodon 登陆，能看到 Mastodon 好友的动态，兼顾社交属性；
- 学习成本低；
NeoDB 也有很多缺点：
- NeoDB 的开放性有所欠缺，由站长 [@alphatownsman](https://github.com/alphatownsman) 一人维护，有些欠缺社区活力；
- 「导出个人数据」功能在优化中；
- 不想豆瓣和 Goodreads，有丰富的扩展和插件，如 [wp-douban](https://github.com/bigfa/wp-douban) （  [示例](https://anotherdayu.com/douban/)）。

我的 NeoDB 主页： https://neodb.social/users/anotherdayu@mastodon.social/ 。
我的 mastodon ID：@anotherdayu@mastodon.social
