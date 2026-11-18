# Setup guide · 配置指南

[English](#english) · [简体中文](#简体中文) · [Rule catalog / 规则索引](rules.md)

## English

[Home](../README.md#english)

### Surge rule sets

1. Choose a list from the [catalog](rules.md) and copy its Surge raw URL.
2. Add `RULE-SET,<raw-url>,<policy>` inside your existing `[Rule]` section. Use
   the name of a proxy or group already defined in your profile, or an intended
   built-in policy such as `DIRECT` or `REJECT`.
3. Place specific rules before broader rules that would otherwise match the
   same request, and before `FINAL`. Save and refresh the rule set in the client.
4. Open the service, then inspect the request's matched rule and final policy.

[Copyable Surge example](../README.md#surge) · [Surge rule matching](https://manual.nssurge.com/rules/overview.html)

### Clash / Mihomo rule providers

1. Copy the Clash / Mihomo raw URL from the [rule catalog](rules.md).
2. Add an entry to the existing top-level `rule-providers` mapping. Use
   `behavior: classical` and `format: yaml` for these YAML files with a `.txt`
   extension. Give each provider a unique name and cache path.
3. Add `RULE-SET,<provider-name>,<policy>` to the existing `rules` list before
   broader matches and `MATCH`. Choose a configured policy or a built-in one
   such as `DIRECT`.
4. Reload the profile, refresh the provider, then inspect a matching connection.

[Copyable Clash / Mihomo example](../README.md#clash--mihomo) · [Mihomo provider options](https://wiki.metacubex.one/en/config/rule-providers/)

### Updates and troubleshooting

Raw links follow `main`. After an upstream change reaches that branch, refresh
the relevant rule set or provider in the client.

| Symptom | Inspect first |
| --- | --- |
| List downloaded, but traffic uses the wrong policy | Earlier matching rules, the target group, and the client's rule mode |
| Provider format error | Use `rules/` for Surge, `clash/` with `classical` / `yaml` for Clash / Mihomo |
| A site is unexpectedly blocked | The matched Reject rule; the personal list includes CSDN and cnblogs |
| A list change has not appeared | The URL's branch and the client's cached list |

For a reproducible report, include the domain, client version, rule file, matched
rule, and expected policy. Remove subscription URLs, tokens, and node credentials
from shared configurations and logs.

### Maintaining rules

- Keep published `.txt` paths stable. They are consumed directly as raw URLs.
- Review both client versions when changing shared coverage. They are manually
  maintained and have [known differences](rules.md#coverage-notes--覆盖说明);
  also consider the separate `AI.txt` aggregate when editing an AI service.
- Add or update the catalog when introducing a list or changing format coverage.
- For Reject changes, update both lists and record the source, reason, count,
  and date. [Reject policy and sources](rules.md#reject-policy-and-sources--reject-策略与来源)
- Keep private subscriptions and generated personal profiles in `local/`.
- Update both languages when editing the overview, setup guide, or rule catalog.

## 简体中文

[首页](../README.md#简体中文)

### Surge 规则集

1. 在[规则索引](rules.md)中选择需要的名单，复制 Surge 对应的原始链接。
2. 在已有的 `[Rule]` 段内添加 `RULE-SET,<raw-url>,<policy>`。策略名应是配置中已经存在的节点或策略组，或者你有意选择的 `DIRECT`、`REJECT` 等内置策略。
3. 把具体规则放在可能先匹配同一请求的宽泛规则之前，并排在 `FINAL` 之前。保存配置，在客户端更新规则集。
4. 打开对应服务，在请求记录中查看实际命中的规则与最终策略。

[可复制的 Surge 示例](../README.md#surge-配置) · [Surge 规则匹配说明](https://manual.nssurge.com/rules/overview.html)

### Clash / Mihomo rule-provider

1. 从[规则索引](rules.md)复制 Clash / Mihomo 一列的原始链接。
2. 在已有的顶层 `rule-providers` 中添加一项。文件扩展名是 `.txt`，内容是 YAML，设置 `behavior: classical` 和 `format: yaml`。每个 provider 使用独立的名称和缓存路径。
3. 将 `RULE-SET,<provider-name>,<policy>` 加入已有的 `rules` 列表，排在宽泛规则和 `MATCH` 之前。使用配置中已有的策略名，或 `DIRECT` 等内置策略。
4. 重新加载配置、更新 provider，再查看连接记录。

[可复制的 Clash / Mihomo 示例](../README.md#clash--mihomo-配置) · [Mihomo provider 参数](https://wiki.metacubex.one/config/rule-providers/)

### 更新与排查

原始链接跟随 `main`。上游修改进入该分支后，在客户端刷新对应规则集或 provider。

| 现象 | 优先检查 |
| --- | --- |
| 名单已下载，但流量走错策略 | 是否有更早命中的规则、目标策略组是否正确、客户端是否处于规则模式 |
| Provider 格式错误 | Surge 使用 `rules/`；Clash / Mihomo 使用 `clash/` 和 `classical` / `yaml` |
| 网站意外被拦截 | 实际命中的 Reject 规则；个人名单包含 CSDN 和博客园 |
| 名单修改尚未生效 | URL 所指分支和客户端缓存 |

反馈问题时，附上域名、客户端版本、规则文件、命中的规则和期望策略。分享配置或日志前，移除订阅 URL、token 和节点凭据。

### 维护规则

- 保持公开 `.txt` 文件的路径稳定，它们直接作为原始订阅地址使用。
- 修改共享覆盖范围时，对照两种客户端格式。它们是手动维护的，存在[已知差异](rules.md#coverage-notes--覆盖说明)；修改 AI 服务时也应考虑独立维护的 `AI.txt` 聚合名单。
- 新增名单或改变格式覆盖情况时，更新规则索引。
- 修改 Reject 时同步两份名单，记录来源、理由、数量和日期。[Reject 策略与来源](rules.md#reject-policy-and-sources--reject-策略与来源)
- 私有订阅与生成的个人配置保存在 `local/`。
- 修改首页、配置指南或规则索引时，同步更新中英文内容。
