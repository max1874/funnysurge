# Rule catalog · 规则索引

[English overview](../README.md) · [中文首页](../README.zh-Hans.md) · [Setup](usage.md) · [配置指南](usage.zh-Hans.md)

Each **Raw** link is a subscription URL on `main`. Surge files contain matching
rules, and you set the policy in your profile. Clash / Mihomo files contain
YAML `payload` lists. A dash marks a rule set available in one format only.

**Raw**（原始链接）可直接用于订阅，跟随 `main`。Surge 文件只有匹配规则，策略在客户端配置中指定。Clash / Mihomo 文件包含 YAML `payload` 列表。「—」表示该名单只提供另一种格式。

## AI services · AI 服务

| List / 名单 | Scope / 内容 | Surge | Clash / Mihomo |
| --- | --- | --- | --- |
| [AI.txt](../rules/AI.txt) | Multiple AI services, Bedrock, and additional domains / 多个 AI 服务、Bedrock 与额外域名 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/AI.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/AI.txt) |
| [OpenAI.txt](../rules/OpenAI.txt) | ChatGPT, Sora, related infrastructure / 相关基础设施 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/OpenAI.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/OpenAI.txt) |
| [Anthropic.txt](../rules/Anthropic.txt) | Claude and related services / Claude 与相关服务 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Anthropic.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Anthropic.txt) |
| [Google-Gemini.txt](../rules/Google-Gemini.txt) | Gemini, AI Studio, Google API domains / Google API 域名 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Google-Gemini.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Google-Gemini.txt) |
| [Apple-Intelligence.txt](../rules/Apple-Intelligence.txt) | Apple Intelligence, Siri, relay domains / 中继域名 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Apple-Intelligence.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Apple-Intelligence.txt) |
| [Microsoft.txt](../rules/Microsoft.txt) | Copilot, Bing | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Microsoft.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Microsoft.txt) |
| [Meta.txt](../rules/Meta.txt) | Meta AI | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Meta.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Meta.txt) |
| [Perplexity.txt](../rules/Perplexity.txt) | Perplexity | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Perplexity.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Perplexity.txt) |
| [OpenRouter.txt](../rules/OpenRouter.txt) | OpenRouter | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/OpenRouter.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/OpenRouter.txt) |
| [X-Grok.txt](../rules/X-Grok.txt) | Grok, x.ai | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/X-Grok.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/X-Grok.txt) |

## Apps and media · 应用与媒体

| List / 名单 | Scope / 内容 | Surge | Clash / Mihomo |
| --- | --- | --- | --- |
| [Cursor.txt](../rules/Cursor.txt) | Domains containing `cursor` / 含 `cursor` 的域名 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Cursor.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Cursor.txt) |
| [Dia.txt](../rules/Dia.txt) | Dia browser / Dia 浏览器 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Dia.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Dia.txt) |
| [Docker.txt](../rules/Docker.txt) | docker.io, ghcr.io | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Docker.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Docker.txt) |
| [Common.txt](../rules/Common.txt) | fonts.gstatic.com | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Common.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Common.txt) |
| [Music.txt](../rules/Music.txt) | Spotify | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Music.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Music.txt) |
| [TikTok.txt](../rules/TikTok.txt) | TikTok, CapCut, ByteDance overseas / 字节海外服务 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/TikTok.txt) | — |
| [PT.txt](../rules/PT.txt) | Private tracker sites / PT 站点 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/PT.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/PT.txt) |

## Interactive Brokers · 盈透证券

| List / 名单 | Scope / 内容 | Surge | Clash / Mihomo |
| --- | --- | --- | --- |
| [IBKR.txt](../rules/IBKR.txt) | TWS, Gateway, API, regional websites / TWS、Gateway、API、地区官网 · [Coverage and sources / 覆盖与来源](#ibkr-coverage-and-sources--ibkr-覆盖与来源) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/IBKR.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/IBKR.txt) |

IBKR is separate from the Futu / moomoo Brokerage list; assign its policy independently.
IBKR 独立于富途 / moomoo 的 Brokerage 名单，单独指定策略。

## Direct and reject · 直连与屏蔽

Use `DIRECT` for Brokerage and DDNS if you want direct routing, and `REJECT`
for Reject if you want to block those connections.

需要直连时，为 Brokerage 和 DDNS 指定 `DIRECT`。需要屏蔽名单中的连接时，为 Reject 指定 `REJECT`。

| List / 名单 | Scope / 内容 | Surge | Clash / Mihomo |
| --- | --- | --- | --- |
| [Brokerage.txt](../rules/Brokerage.txt) | Futu / 富途, moomoo | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Brokerage.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Brokerage.txt) |
| [DDNS.txt](../rules/DDNS.txt) | IP lookup, DDNS, time.is / IP 查询、DDNS、time.is | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/DDNS.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/DDNS.txt) |
| [Reject.txt](../rules/Reject.txt) | Personal blocklist / 个人屏蔽名单 · [Policy and sources / 策略与来源](#reject-policy-and-sources--reject-策略与来源) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Reject.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Reject.txt) |

## Coverage notes · 覆盖说明

The two formats are maintained by hand. Known differences in the published files:

- `TikTok.txt` exists only in Surge format.
- Surge's `OpenAI.txt` and `AI.txt` include `chat.com`, `crixet.com`,
  `oaistatsig.com`, and the `chatgpt-async-webps` keyword; the Clash versions do not.
- Surge's `PT.txt` includes `qingwapt.com` and matches `pterclub.net` by suffix;
  Clash omits `qingwapt.com` and matches the broader `pterclub` keyword.

两种格式均为手工维护，已知差异如下。

- `TikTok.txt` 只有 Surge 版。
- Surge 的 `OpenAI.txt` 和 `AI.txt` 包含 `chat.com`、`crixet.com`、`oaistatsig.com` 和关键词 `chatgpt-async-webps`。Clash 版缺少这些条目。
- Surge 的 `PT.txt` 包含 `qingwapt.com`，并按后缀匹配 `pterclub.net`。Clash 版省略了 `qingwapt.com`，用范围更广的关键词 `pterclub` 匹配。

`AI.txt` is a separately maintained aggregate, including shared infrastructure
and some Gemini-protocol domains unrelated to Google's Gemini service. Review
its content before choosing it over individual service lists.

`AI.txt` 是独立维护的聚合名单，包含共享基础设施，以及与 Google Gemini 无关的 Gemini 协议域名。选择聚合名单前请先查看其内容。

<a name="ibkr-覆盖与来源"></a>

### IBKR coverage and sources · IBKR 覆盖与来源

The initial lists, compiled on 2026-10-09, contain the same 26 `DOMAIN-SUFFIX`
rules in both formats. They cover known TWS and Gateway infrastructure, APIs,
websites, and guides. IP-only connections and third-party services may need
additional rules. The entries come from public lists and connection logs.
Verify trading connections in the client you use.

2026-10-09 首次整理，两种格式各有 26 条相同的 `DOMAIN-SUFFIX` 规则，覆盖已收录的 TWS / Gateway、API、官网和指南。纯 IP 连接和第三方服务可能需要另外设置。这些条目来自公开名单与连接记录，交易连接的验证应在实际客户端完成。

| Source / 来源 | Coverage / 覆盖 |
| --- | --- |
| [v2fly/domain-list-community](https://github.com/v2fly/domain-list-community/blob/master/data/ibkr) | 21 core and regional domains / 21 个核心及地区域名 |
| [GravityPoet / IBKR.list](https://gist.github.com/GravityPoet/4b67598168e7b4b4a222f130405458e1) | Additional domains / 补充域名 · `ibllc.com.cn`, `ibkr.info`, `ibkr.hk`, `interactivebrokers.com.cn`, `ibkr.com.cn` |
| Surge request log / Surge 请求记录 (2026-10-09) | Covered by suffix rules / 已由后缀规则覆盖 · `api.ibkr.com`, `sdc1-hb1.ibllc.com`, `sdc1-hb2.ibllc.com`, `sdc1.ibllc.com`, `hdc1.ibllc.com`, `download2.interactivebrokers.com` |

On Surge for Mac, open the request details to find Gateway's process path if
you need to route its IP-only connections. Use the actual path in a
`PROCESS-NAME` rule because other Java apps can share the executable name
`JavaApplicationStub`. [Surge process rules](https://manual.nssurge.com/rules/process.html)

Surge Mac 用户如需对 Gateway 的纯 IP 连接补充分流，可在请求详情中查看进程路径，再按实际路径添加 `PROCESS-NAME` 规则。它可能显示为多个 Java 应用共用的 `JavaApplicationStub`，宜使用路径区分。[Surge 进程规则](https://manual.nssurge.com/rules/process.html)

When maintaining the lists, check who operates each domain using requests
observed during login, market-data access, or downloads. For shared third-party
services, prefer exact hostnames supported by those observations. Update both
lists, record the source, then refresh the rules and open a new connection to
check the match and policy.

维护时根据登录、行情或下载等操作中的实际请求核对域名归属。共享第三方服务优先采用有证据的精确主机名。同步更新两份名单并记录来源，再刷新规则集、新建连接，检查命中规则和策略。

<a name="reject-策略与来源"></a>

### Reject policy and sources · Reject 策略与来源

This hand-curated personal blocklist initially contained 19 domains on
2026-09-08. `DOMAIN-SUFFIX` rules cover each listed domain and its subdomains.
To enable the list, assign it the `REJECT` policy and place it before broader
direct-routing rules.

这是手动筛选的个人屏蔽名单，首次整理于 2026-09-08，共 19 个域名。`DOMAIN-SUFFIX` 规则覆盖域名及其子域名。需要启用时，为规则集指定 `REJECT` 并排在宽泛直连规则之前。

| Domains / 域名 | Original source / 首次采用的来源 |
| --- | --- |
| `cnblogs.com`, `csdn.net` | User request / 用户指定 |
| `codeantenna.com`, `cxyzjd.com` | Listed by both sources / 两份名单均收录 · [inkss](https://gist.github.com/inkss/6a256813ad2df862d1f8b91f6db0c643) · [cobaltdisco exact matches / 精确匹配](https://raw.githubusercontent.com/cobaltdisco/Google-Chinese-Results-Blocklist/master/uBlacklist_subscription.txt) |
| `adoclib.com`, `askdev.ru`, `cdmana.com`, `chowdera.com`, `code-examples.net`, `codeleading.com`, `codenong.com`, `codeprj.com`, `codetd.com`, `coder.work`, `coderoad.ru`, `copyfuture.com`, `copyprogramming.com`, `cxybb.com`, `cxymm.net` | [cobaltdisco / Google-Chinese-Results-Blocklist](https://github.com/cobaltdisco/Google-Chinese-Results-Blocklist) |

Review new entries by full domain name and keep the source's subdomain scope.
Exclude entries that require a page path, query parameter, or title pattern
to match. Use third-party lists to find candidates, and independently check
shared sites such as cloud platforms, software mirrors, and communities.
Update both formats and record the source, reason, count, and date. Remove
false positives from both lists.

新增条目时按完整域名核对，保留来源指定的子域名范围，排除仅靠文章路径、查询参数或标题模式才能匹配的条目。第三方名单用于发现候选条目，云平台、软件镜像和社区等共享站点需要独立核对。同步维护两份规则，记录来源、理由、数量和日期。误拦截时从两份规则中移除。

Additional candidate list / 候选条目参考 · [scyrte / uBlacklist-Subscription](https://github.com/scyrte/uBlacklist-Subscription)
