# 配置指南

[首页](../README.zh-Hans.md) · [规则索引](rules.md) · [English](usage.md)

## Surge 规则集

1. 在[规则索引](rules.md)中选择需要的名单，复制 Surge 对应的原始链接。
2. 在已有的 `[Rule]` 段内添加 `RULE-SET,<raw-url>,<policy>`。策略名应是配置中已经存在的节点或策略组，或者你有意选择的 `DIRECT`、`REJECT` 等内置策略。
3. 把具体规则放在可能先匹配同一请求的宽泛规则之前，并排在 `FINAL` 之前。保存配置，在客户端更新规则集。
4. 打开对应服务，在请求记录中查看实际命中的规则与最终策略。

需要统一分流多个 AI 服务时可选择 `AI.txt`。需要分别指定策略时用独立名单。如果两者都用，把具体服务的覆盖规则放在前面。[Surge 快速开始](../README.zh-Hans.md#surge)

匹配行为参考 Surge 的[规则系统文档](https://manual.nssurge.com/rules/overview.html)。

## Clash / Mihomo rule-provider

使用 `clash/` 下的文件，设置 `behavior: classical` 和 `format: yaml`。为兼容已有订阅，扩展名保留 `.txt`，文件内容实际是 YAML `payload` 列表。

把 provider 定义添加到顶层的 `rule-providers` 映射，把匹配规则添加到 `rules` 列表。每个 provider 使用独立的名称和缓存路径。将 `PROXY` 替换成已有策略名。[Clash / Mihomo 快速开始](../README.zh-Hans.md#clash--mihomo)

把 `RULE-SET` 条目排在宽泛匹配和 `MATCH` 之前。重新加载配置、更新 provider，再查看连接记录。示例的更新间隔是 86,400 秒，也可以手动提前刷新。参数含义见 [Mihomo 官方文档](https://wiki.metacubex.one/config/rule-providers/)。

## 更新与排查

原始链接跟随 `main`。上游修改进入该分支后，在客户端刷新对应规则集或 provider。

| 现象 | 优先检查 |
| --- | --- |
| 名单已下载，但流量走错策略 | 是否有更早命中的规则、目标策略组是否正确、客户端是否处于规则模式 |
| Provider 格式错误 | Surge 使用 `rules/`；Clash / Mihomo 使用 `clash/` 和 `classical` / `yaml` |
| 网站意外被拦截 | 实际命中的 Reject 规则；个人名单包含 CSDN 和博客园 |
| 名单修改尚未生效 | URL 所指分支和客户端缓存 |

反馈问题时，附上域名、客户端版本、规则文件、命中的规则和期望策略。分享配置或日志前，移除订阅 URL、token 和节点凭据。

## 维护规则

- 保持公开 `.txt` 文件的路径稳定，它们直接作为原始订阅地址使用。
- 修改共享覆盖范围时，对照两种客户端格式。它们是手动维护的，存在[已知差异](rules.md#coverage-notes--覆盖说明)；修改 AI 服务时也应考虑独立维护的 `AI.txt` 聚合名单。
- 新增名单或改变格式覆盖情况时，更新规则索引。
- 修改 Reject 时同步两份名单，并在 [reject.md](reject.md) 中记录来源、理由、数量和日期。
- 私有订阅与生成的个人配置保存在 `local/`。
- 首页与配置指南的两种语言版本保持同步。
