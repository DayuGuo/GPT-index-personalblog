今天，OpenAI 发布了 ChatGPT API（gpt-3.5-turbo），每 1k 个 tokens 的价格为 0.002 美元，比之前的 GPT-3.5 模型便宜 10 倍。
但 API 的形式对普通用户来说并不算友好，本文将介绍几种使用 ChatGPT API 的方法，并持续在[个人网站](https://anotherdayu.com/)中更新。
# Bob 翻译插件
[Bob](https://bobtranslate.com/) 是一款非常优秀的 macOS 翻译软件，非常推荐购买。
之前一直用的是 DeepL 的插件，比 GPT 3.0 API 的速度快很多，但 gpt-3.5-turbo 更新后，翻译速度得到了明显的提升，完全可以作为主力使用。
![[CleanShot 2023-03-02 at 19.55.31@2x.png]]
**安装教程：** 首先，准备 OpenAI 的账户，打开 API keys 页面： https://platform.openai.com/account/api-keys 。点击 `create new secret key`，即可生成 API。
![[CleanShot 2023-03-02 at 20.07.13@2x.png]]
下载 Bob 付费版，并设置 macOS 软件权限。
确认 Bob 在后台运行，下载插件：[openai-translator.bobplugin](https://github.com/yetone/bob-plugin-openai-translator/releases)，并打开 `openai-translator.bobplugin` ，即可安装成功。
![[CleanShot 2023-03-02 at 20.02.34@2x.png]]
- 之后，需要在 Bob 的「设置-服务」中点击 `+`，启用 OpenAI API。
- 然后在「服务」中，填入 API Key，选择模型 `gpt-3.5-turbo-0301`，点击保存。
- `gpt-3.5-turbo-0301` 和 `gpt-3.5-turbo` 好像没有区别。
![[CleanShot 2023-03-02 at 20.04.07@2x.png]]
# Popclip - 随时随地使用 ChatGPT API
Notion Ai 使用起来非常方便，但只能在 Notion 内使用，Popclip 论坛中的一位[老哥](https://forum.popclip.app/t/a-popclip-extension-for-chatgpt-updated/1283/18)实现了这一点。这个插件只要在文本编辑器中，就能使用，如 Obsidian 和 Words，甚至是微信、Telegram 的聊天窗口。
安装教程：首先，安装 Popclip，并设置 macOS 软件权限。
确认 Popclip 正在运行，选中以下代码，就会跳出 Popclip 的插件安装选项：「Install Extension」，点击即可完成安装。

```
// #popclip extension for ChatGPT
// name: ChatGPT
// icon: iconify:logos:openai-icon
// language: javascript
// module: true
// entitlements: [network]
// options: [{
//   identifier: apikey, label: API Key, type: string,
//   description: 'Obtain API key from https://platform.openai.com/account/api-keys'
// }]
const messages = []; // history of previous messages
async function chat (input, options) {
  const openai = require("axios").create({
    baseURL: "https://api.openai.com/v1",
    headers: { Authorization: `Bearer ${options.apikey}` },
  });
  messages.push({ "role": "user", "content": input.text });
  const { data } = await openai.post("/chat/completions", {
    model: "gpt-3.5-turbo", messages
  });
  messages.push(data.choices[0].message);
  return input.text.trimEnd() + "\n\n" + messages.at(-1).content.trim();
};
exports.actions = [{
  title: "ChatGPT: Chat",
  after: "paste-result",
  code: chat,
}, {
  title: "ChatGPT: Reset",
  icon: "iconify:game-icons:broom",
  requirements: [],
  after: "show-status",
  code: () => messages.length = 0 // clear the message history
}];
```
然后，点击图标即可使用（下图 gif 的测试环境是 Obsidian）。
另外，有一个扫帚形状的图标，可以重置聊天记录，开始新对话。
![[CleanShot 2023-03-02 at 21.08.18.gif]]
# Siri + 快捷指令 = ChatGPT Siri

先下载以下两个快捷指令（原作者不详，有知道的请在评论区留言），然后点击添加。
GPT3.5 X Siri - 语音版尝鲜 https://www.icloud.com/shortcuts/a8e39045960641549c603c97397cf888
GPT3.5 X Siri - 文字版尝鲜 https://www.icloud.com/shortcuts/dc8f48a94b4b44a1ac22c0d486269492
要更改快捷指令的名称，系统语言是中文的话，也要将快捷指令的名称改为中文（英文语言的话，快捷指令也是英文的名字）。
可以点击启动，也可以通过 Siri 启动。
启动 Siri 的时候慢一些，比如我的快捷指令名叫「小西瓜」。那么说完「Hi，Siri！」之后，停顿一下，再说「小西瓜」，等手机显示「Hello, I'm GPT!」，再说指令。
![[CleanShot 2023-03-02 at 21.41.14@2x.png]]

# 其他
这里分享一些有趣的 OpenAI API 应用，但都非刚需。
- 使用 OpenAI API 翻译电子书：[bilingual_book_maker](https://github.com/yihong0618/bilingual_book_maker)，每本书大概花费在 3 美元左右。
- 将小爱同学接入 chatGPT API：[xiaogpt](https://github.com/yihong0618/xiaogpt)。