# 规则索引

[项目首页](../README.zh-Hans.md) · [配置指南](usage.zh-Hans.md) · [English](rules.md)

从最后一列复制对应客户端的链接。需要代理时选已有策略组，直连用 `DIRECT`，屏蔽用 `REJECT`。[Surge 规则文件](../rules/) · [Clash / Mihomo 规则文件](../clash/)

## AI 服务

| 规则集 | 覆盖范围 | 订阅链接 |
| --- | --- | --- |
| AI 服务合集 | 多个 AI 服务与 Bedrock | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/AI.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/AI.txt) |
| OpenAI | ChatGPT、Sora 和相关域名 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/OpenAI.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/OpenAI.txt) |
| Anthropic | Claude 与相关服务 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Anthropic.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Anthropic.txt) |
| Google Gemini | Gemini、AI Studio 和 Google API | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Google-Gemini.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Google-Gemini.txt) |
| Apple Intelligence | Apple Intelligence、Siri 和中继域名 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Apple-Intelligence.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Apple-Intelligence.txt) |
| Microsoft | Copilot 和必应 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Microsoft.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Microsoft.txt) |
| Meta | Meta AI | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Meta.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Meta.txt) |
| Perplexity | Perplexity | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Perplexity.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Perplexity.txt) |
| OpenRouter | OpenRouter | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/OpenRouter.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/OpenRouter.txt) |
| Grok | Grok 和 x.ai | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/X-Grok.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/X-Grok.txt) |

## 应用与媒体

| 规则集 | 覆盖范围 | 订阅链接 |
| --- | --- | --- |
| Cursor | 包含 `cursor` 的域名 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Cursor.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Cursor.txt) |
| Dia | Dia 浏览器 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Dia.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Dia.txt) |
| Docker | Docker Hub 和 GitHub 容器镜像仓库 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Docker.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Docker.txt) |
| Google Fonts | 由 `fonts.gstatic.com` 提供的字体 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Common.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Common.txt) |
| Spotify | Spotify | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Music.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Music.txt) |
| TikTok | TikTok、CapCut 和字节海外服务 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/TikTok.txt) |
| PT 站点 | 私有 Tracker 站点 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/PT.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/PT.txt) |

## 金融、直连与屏蔽

| 规则集 | 覆盖范围 | 订阅链接 |
| --- | --- | --- |
| [盈透证券](#ibkr-覆盖与来源) | TWS、Gateway、API 和官网 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/IBKR.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/IBKR.txt) |
| 富途与 moomoo | 券商服务 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Brokerage.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Brokerage.txt) |
| DDNS | DDNS、IP 查询和 time.is | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/DDNS.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/DDNS.txt) |
| [Reject](#reject-策略与来源) | 个人屏蔽名单，包含 CSDN 和博客园 | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Reject.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Reject.txt) |

## 覆盖说明

- **AI：** `AI.txt` 与各服务的规则集独立维护，包含共享基础设施，也包含与 Google Gemini 无关的 Gemini 协议域名。
- **OpenAI：** Surge 版的 `OpenAI.txt` 和 `AI.txt` 还匹配 `chat.com`、`crixet.com`、`oaistatsig.com` 和关键词 `chatgpt-async-webps`。
- **PT：** Surge 包含 `qingwapt.com`，并按后缀匹配 `pterclub.net`。Clash 使用范围更广的关键词 `pterclub`，省略了 `qingwapt.com`。
- **TikTok：** 仅提供 Surge 版。

### IBKR 覆盖与来源

盈透证券用 IBKR，富途或 moomoo 用 Brokerage，可分别指定策略。IBKR 的两种格式以相同的 26 条域名后缀规则起步。请在客户端检查实际交易连接，尤其是直接连 IP 的请求。

如果要用 Surge Mac 给 Gateway 的纯 IP 连接分流，可以在连接详情里复制实际进程路径，再添加 `PROCESS-NAME` 规则。其他 Java 应用可能共用 `JavaApplicationStub` 这个名称。[Surge 进程规则](https://manual.nssurge.com/rules/process.html)

<details>
<summary>来源与维护细节</summary>

名单首次整理于 2026-10-09。

- 21 个核心及地区域名。[v2fly/domain-list-community](https://github.com/v2fly/domain-list-community/blob/master/data/ibkr)
- 另外补充 5 个域名，分别是 `ibllc.com.cn`, `ibkr.info`, `ibkr.hk`, `interactivebrokers.com.cn`, `ibkr.com.cn`。[GravityPoet / IBKR.list](https://gist.github.com/GravityPoet/4b67598168e7b4b4a222f130405458e1)
- 当天的 Surge 请求记录里出现了 `api.ibkr.com`, `sdc1-hb1.ibllc.com`, `sdc1-hb2.ibllc.com`, `sdc1.ibllc.com`, `hdc1.ibllc.com`, `download2.interactivebrokers.com`，均由后缀规则覆盖。

添加域名时，从实际登录、行情或下载连接里确认域名用途。对共享第三方基础设施，优先使用精确主机名。同步更新两份规则并记录来源，再刷新并重连，检查命中结果。

</details>

### Reject 策略与来源

这是按需启用的个人屏蔽名单。为规则集指定 `REJECT` 并排在宽泛的直连规则之前，即可屏蔽名单中的域名及其子域名。

<details>
<summary>来源与维护细节</summary>

首次名单整理于 2026-09-08，共 19 个域名。

- 用户指定了 `cnblogs.com` 和 `csdn.net`。
- 两份来源都收录了 `codeantenna.com` 和 `cxyzjd.com`。[inkss](https://gist.github.com/inkss/6a256813ad2df862d1f8b91f6db0c643) · [cobaltdisco 精确匹配名单](https://raw.githubusercontent.com/cobaltdisco/Google-Chinese-Results-Blocklist/master/uBlacklist_subscription.txt)
- 其余首批域名为 `adoclib.com`, `askdev.ru`, `cdmana.com`, `chowdera.com`, `code-examples.net`, `codeleading.com`, `codenong.com`, `codeprj.com`, `codetd.com`, `coder.work`, `coderoad.ru`, `copyfuture.com`, `copyprogramming.com`, `cxybb.com`, `cxymm.net`。[cobaltdisco](https://github.com/cobaltdisco/Google-Chinese-Results-Blocklist)

第三方名单用来发现候选条目。逐个检查完整域名和子域名范围，尤其是共享平台。只匹配某篇文章、查询参数或标题的条目放在其他名单。同步更新两种格式，记录来源、理由、数量和日期，误拦截时从两份名单移除。[候选条目参考](https://github.com/scyrte/uBlacklist-Subscription)

</details>
