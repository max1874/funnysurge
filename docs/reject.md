# 自维护 Reject 名单

本仓库手动筛选并维护域名，外部名单仅用于发现候选项，不自动全量同步。
本名单是个人访问偏好，不是恶意网站判定名单。

- Surge：[`rules/Reject.txt`](../rules/Reject.txt)，由 `base.conf` 以 `REJECT` 策略引用。
- Clash：[`clash/Reject.txt`](../clash/Reject.txt)，使用 `behavior: classical` 的 rule-provider，并绑定 `REJECT` 策略。
- `DOMAIN-SUFFIX` 阻止域名及其所有子域名的连接，不会隐藏搜索结果。
- 首次整理：2026-09-08，共 19 个域名。来源收录不代表已逐站核实当前内容。

## 来源与筛选

| 来源 | 本次采用的域名 |
| --- | --- |
| 用户明确指定 | `cnblogs.com`、`csdn.net` |
| [inkss 中文搜索屏蔽名单](https://gist.github.com/inkss/6a256813ad2df862d1f8b91f6db0c643) 与 [cobaltdisco 精确匹配名单](https://raw.githubusercontent.com/cobaltdisco/Google-Chinese-Results-Blocklist/master/uBlacklist_subscription.txt) 均收录 | `codeantenna.com`、`cxyzjd.com` |
| [cobaltdisco / Google-Chinese-Results-Blocklist](https://github.com/cobaltdisco/Google-Chinese-Results-Blocklist) 的精确匹配名单 | `adoclib.com`、`askdev.ru`、`cdmana.com`、`chowdera.com`、`code-examples.net`、`codeleading.com`、`codenong.com`、`codeprj.com`、`coder.work`、`coderoad.ru`、`codetd.com`、`copyfuture.com`、`copyprogramming.com`、`cxybb.com`、`cxymm.net` |

[scyrte / uBlacklist-Subscription](https://github.com/scyrte/uBlacklist-Subscription) 可作为后续候选来源；本次没有从中新增条目。

## 维护约定

1. 优先收录用户明确指定的站点，以及来源名单中的技术采集、翻译镜像站候选域名；新增时记录来源与理由。
2. 只采用可以表达为完整域名的条目。文章路径、查询参数、标题正则不能提升为整个域名的屏蔽规则。
3. 不因外部名单收录而直接拉黑云平台、代码托管、软件包镜像或整个社区。本次未采用腾讯云、阿里云、华为云、Gitee、简书、掘金、51CTO 等条目。
4. 保留来源指定的子域名范围，不擅自提升到父域名；同一后缀覆盖的条目去重。
5. 修改时同步 Surge 与 Clash 两份名单，并更新本文来源、数量和整理日期。发现误拦截时从两份名单一起移除。
6. `base.conf` 中的自维护名单位于宽泛直连规则之前。发布到 `main` 后，远程订阅地址才包含新内容；客户端需更新配置及规则集。

现有第三方广告 Reject 订阅继续独立维护。本文件不包含定时抓取或自动更新任务。
