#Permanent
[[Blog_MOC]] 

# 需求
在运行代理的情况（规则判定）下，Google 等网站能正常访问，但 macOS 版 Telegram 无法正常连接网络，报错：「Connecting to Proxy」。
![[Pasted image 20220519130334.png]]
# 解决方法
## 方案一
打开全局代理
## 方案二
下载 Clash X Pro 或 Surge 等软件，使用「增强模式」。
## 方案三
- 配置 Telegram 的代理设置，先打开你使用的代理软件，点击「复制终端代理命令」,如下
```
export https_proxy=http://127.0.0.1:6152;export http_proxy=http://127.0.0.1:6152;export all_proxy=socks5://127.0.0.1:6153
```

- 其中的 `127.0.0.1:6153` 是我们需要的部分，这部分不同代理软件和个人设置会有不同。
- 打开 Telegram - Setting - Data and Storage - Use Proxy - 点击 Add Proxy
- 选择 SOCKS5
- 在 Connection 部分， Server 中填写 127.0.0.1，Port 中填写：6153。
- 点击完成即可

![[Pasted image 20220519130015.png]]
