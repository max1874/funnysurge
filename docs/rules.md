# Rule catalog

[Overview](../README.md) · [Setup guide](usage.md) · [简体中文](rules.zh-Hans.md)

Copy the link for your client from the last column. Use an existing policy group for proxy traffic, `DIRECT` for direct connections, or `REJECT` to block a match. [Surge files](../rules/) · [Clash / Mihomo files](../clash/)

## AI services

| Rule set | Coverage | Subscription URLs |
| --- | --- | --- |
| AI services | Multiple AI services and Bedrock | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/AI.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/AI.txt) |
| OpenAI | ChatGPT, Sora, and supporting domains | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/OpenAI.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/OpenAI.txt) |
| Anthropic | Claude and related services | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Anthropic.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Anthropic.txt) |
| Google Gemini | Gemini, AI Studio, and Google APIs | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Google-Gemini.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Google-Gemini.txt) |
| Apple Intelligence | Apple Intelligence, Siri, and relays | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Apple-Intelligence.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Apple-Intelligence.txt) |
| Microsoft | Copilot and Bing | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Microsoft.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Microsoft.txt) |
| Meta | Meta AI | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Meta.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Meta.txt) |
| Perplexity | Perplexity | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Perplexity.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Perplexity.txt) |
| OpenRouter | OpenRouter | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/OpenRouter.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/OpenRouter.txt) |
| Grok | Grok and x.ai | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/X-Grok.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/X-Grok.txt) |

## Apps and media

| Rule set | Coverage | Subscription URLs |
| --- | --- | --- |
| Cursor | Domains containing `cursor` | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Cursor.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Cursor.txt) |
| Dia | Dia browser | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Dia.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Dia.txt) |
| Docker | Docker Hub and GitHub Container Registry | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Docker.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Docker.txt) |
| Google Fonts | `fonts.gstatic.com` | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Common.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Common.txt) |
| Spotify | Spotify | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Music.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Music.txt) |
| TikTok | TikTok, CapCut, and ByteDance overseas services | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/TikTok.txt) |
| Private trackers | Private tracker sites | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/PT.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/PT.txt) |

## Finance, direct routing, and blocking

| Rule set | Coverage | Subscription URLs |
| --- | --- | --- |
| [IBKR](#ibkr-coverage-and-sources) | TWS, Gateway, APIs, and websites | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/IBKR.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/IBKR.txt) |
| Futu and moomoo | Brokerage services | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Brokerage.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Brokerage.txt) |
| DDNS | DDNS, IP lookup, and time.is | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/DDNS.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/DDNS.txt) |
| [Reject](#reject-policy-and-sources) | Personal blocklist, including CSDN and cnblogs | [Surge](https://raw.githubusercontent.com/max1874/funnysurge/main/rules/Reject.txt) · [Clash / Mihomo](https://raw.githubusercontent.com/max1874/funnysurge/main/clash/Reject.txt) |

<a name="coverage-notes--覆盖说明"></a>

## Coverage notes

- **AI:** `AI.txt` is maintained independently of the individual lists. It includes shared infrastructure and some Gemini-protocol domains unrelated to Google's Gemini service.
- **OpenAI:** The Surge versions of `OpenAI.txt` and `AI.txt` also match `chat.com`, `crixet.com`, `oaistatsig.com`, and the keyword `chatgpt-async-webps`.
- **PT:** Surge includes `qingwapt.com` and matches the `pterclub.net` suffix. Clash uses the broader `pterclub` keyword and omits `qingwapt.com`.
- **TikTok:** Available for Surge only.

<a name="ibkr-coverage-and-sources--ibkr-覆盖与来源"></a>
<a name="ibkr-覆盖与来源"></a>

### IBKR coverage and sources

Use IBKR for Interactive Brokers and Brokerage for Futu or moomoo. Assign a policy to each list. The two IBKR formats start from the same 26 domain suffixes. Check trading connections in your client, especially connections made directly to an IP address.

On Surge for Mac, you can route Gateway's IP-only connections with `PROCESS-NAME`. Copy the actual process path from the connection details. Other Java apps can share the name `JavaApplicationStub`. [Surge process rules](https://manual.nssurge.com/rules/process.html)

<details>
<summary>Source and maintenance details</summary>

Initial lists compiled on 2026-10-09.

- 21 core and regional domains. [v2fly/domain-list-community](https://github.com/v2fly/domain-list-community/blob/master/data/ibkr)
- Five additional domains: `ibllc.com.cn`, `ibkr.info`, `ibkr.hk`, `interactivebrokers.com.cn`, `ibkr.com.cn`. [GravityPoet / IBKR.list](https://gist.github.com/GravityPoet/4b67598168e7b4b4a222f130405458e1)
- The Surge request log on that date showed `api.ibkr.com`, `sdc1-hb1.ibllc.com`, `sdc1-hb2.ibllc.com`, `sdc1.ibllc.com`, `hdc1.ibllc.com`, `download2.interactivebrokers.com`. The suffix rules cover those hosts.

For a new domain, confirm its role in a real login, market-data, or download connection. Prefer an exact hostname on shared third-party infrastructure. Update both lists, record the source, then refresh and reconnect to verify the match.

</details>

<a name="reject-policy-and-sources--reject-策略与来源"></a>
<a name="reject-策略与来源"></a>

### Reject policy and sources

This is an opt-in personal blocklist. Assign it the `REJECT` policy and place it above broader direct rules to block connections to each listed domain and its subdomains.

<details>
<summary>Source and maintenance details</summary>

The initial list contained 19 domains on 2026-09-08.

- User requested `cnblogs.com` and `csdn.net`.
- Both source lists include `codeantenna.com` and `cxyzjd.com`. [inkss](https://gist.github.com/inkss/6a256813ad2df862d1f8b91f6db0c643) · [cobaltdisco exact matches](https://raw.githubusercontent.com/cobaltdisco/Google-Chinese-Results-Blocklist/master/uBlacklist_subscription.txt)
- Other initial domains: `adoclib.com`, `askdev.ru`, `cdmana.com`, `chowdera.com`, `code-examples.net`, `codeleading.com`, `codenong.com`, `codeprj.com`, `codetd.com`, `coder.work`, `coderoad.ru`, `copyfuture.com`, `copyprogramming.com`, `cxybb.com`, `cxymm.net`. [cobaltdisco](https://github.com/cobaltdisco/Google-Chinese-Results-Blocklist)

Use external lists to find candidates. Check the full domain and subdomain scope, especially on shared platforms. Entries that require a particular page, query string, or title are outside this list's scope. Update both formats, record the source, reason, count, and date, and remove false positives from both. [Additional candidate list](https://github.com/scyrte/uBlacklist-Subscription)

</details>
