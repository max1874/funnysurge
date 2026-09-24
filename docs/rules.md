# Rule catalog · 规则索引

[English overview](../README.md) · [中文首页](../README.zh-Hans.md) · [Setup](usage.md) · [配置指南](usage.zh-Hans.md)

Each **Raw** link is a subscription URL on `main`. Use the filename link to read
the Surge source; browse [clash/](../clash/) for the YAML versions. A dash means
that client format is not published.

**Raw** 链接可直接用于订阅，跟随 `main`。文件名链接可查看 Surge 原文；YAML 版本见 [clash/](../clash/)。「—」表示暂未提供该格式。

## AI services · AI 服务

| List / 名单 | Scope / 内容 | Surge | Clash / Mihomo |
| --- | --- | --- | --- |
| [AI.txt](../rules/AI.txt) | Multiple AI services, Bedrock, and additional domains / 多服务聚合与额外域名 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/AI.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/AI.txt) |
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
| [Cursor.txt](../rules/Cursor.txt) | Domains containing `cursor` / 域名关键词匹配 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Cursor.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Cursor.txt) |
| [Dia.txt](../rules/Dia.txt) | Dia browser / Dia 浏览器 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Dia.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Dia.txt) |
| [Docker.txt](../rules/Docker.txt) | docker.io, ghcr.io | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Docker.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Docker.txt) |
| [Education.txt](../rules/Education.txt) | Education email tutorial sites / 教育邮箱教程相关站点 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Education.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Education.txt) |
| [Common.txt](../rules/Common.txt) | fonts.gstatic.com | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Common.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Common.txt) |
| [Music.txt](../rules/Music.txt) | Spotify | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Music.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Music.txt) |
| [TikTok.txt](../rules/TikTok.txt) | TikTok, CapCut, ByteDance overseas / 字节海外服务 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/TikTok.txt) | — |
| [PT.txt](../rules/PT.txt) | Private tracker sites / PT 站点 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/PT.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/PT.txt) |

## Direct and reject · 直连与屏蔽

The base profile assigns `DIRECT` to Brokerage and DDNS, and `REJECT` to Reject.
Each list itself contains only matching rules; you choose the policy.

基础配置将 Brokerage、DDNS 设为 `DIRECT`，Reject 设为 `REJECT`。名单本身只定义匹配条件，策略由你决定。

| List / 名单 | Scope / 内容 | Surge | Clash / Mihomo |
| --- | --- | --- | --- |
| [Brokerage.txt](../rules/Brokerage.txt) | Futu / 富途, moomoo | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Brokerage.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Brokerage.txt) |
| [DDNS.txt](../rules/DDNS.txt) | IP lookup, DDNS, time.is / IP 查询与工具 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/DDNS.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/DDNS.txt) |
| [Reject.txt](../rules/Reject.txt) | Personal blocklist; [policy and sources](reject.md) / 个人屏蔽名单 | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Reject.txt) | [Raw](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Reject.txt) |

## Coverage notes · 覆盖说明

The two formats are maintained by hand. Known differences in the published files:

- `TikTok.txt` exists only in Surge format.
- Surge's `OpenAI.txt` and `AI.txt` include `chat.com`, `crixet.com`,
  `oaistatsig.com`, and the `chatgpt-async-webps` keyword; the Clash versions do not.
- Surge's `PT.txt` includes `qingwapt.com` and matches `pterclub.net` by suffix;
  Clash omits `qingwapt.com` and matches the broader `pterclub` keyword.

两种格式均为手工维护。当前 TikTok 只有 Surge 版；Surge 的 OpenAI / AI 比 Clash 多出上述三个域名与一个关键词；PT 则在 `qingwapt.com` 和 `pterclub` 的匹配范围上存在差异。

`AI.txt` is a separately maintained aggregate, including shared infrastructure
and some Gemini-protocol domains unrelated to Google's Gemini service. Review
its content before choosing it over individual service lists.

`AI.txt` 是独立维护的聚合名单，包含共享基础设施，以及与 Google Gemini 无关的 Gemini 协议域名。选择聚合名单前请先查看其内容。
