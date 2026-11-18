# 配置指南

[项目首页](../README.zh-Hans.md) · [规则索引](rules.zh-Hans.md) · [English](usage.md)

从一份能正常使用的配置开始，把示例中的 `PROXY` 换成配置里已有的代理或策略组名称。

## Surge

把这一行加到现有的 `[Rule]` 段，排在可能先命中的宽泛规则和 `FINAL` 前面。

```ini
RULE-SET,https://raw.githubusercontent.com/max1874/funnysurge/main/rules/OpenAI.txt,PROXY
```

保存配置后更新规则集。要给其他服务分流，把 URL 换成该服务的 **Surge** 订阅链接。[规则索引](rules.zh-Hans.md) · [Surge 规则集文档](https://manual.nssurge.com/rules/ruleset.html)

## Clash / Mihomo

在 `rule-providers` 下添加 `funnysurge-openai`，再把 `RULE-SET` 条目加到 `rules`。合并到已有的配置键中，把规则排在可能先命中的宽泛规则和 `MATCH` 前面。

```yaml
rule-providers:
  funnysurge-openai:
    type: http
    behavior: classical
    format: yaml
    url: https://raw.githubusercontent.com/max1874/funnysurge/main/clash/OpenAI.txt
    path: ./rule-providers/funnysurge-openai.yaml
    interval: 86400

rules:
  - RULE-SET,funnysurge-openai,PROXY
```

重新加载配置并更新规则提供器。要添加其他服务，使用它的 **Clash / Mihomo** 订阅链接，为新提供器指定独立的名称和缓存路径。提供器的名称要和 `RULE-SET` 里的一致。[规则索引](rules.zh-Hans.md) · [Mihomo 规则提供器文档](https://wiki.metacubex.one/config/rule-providers/)

## 查看命中结果

使用规则模式打开 `chatgpt.com`。在客户端找到一条访问该域名的新连接，核对是否命中 OpenAI 规则集，并使用你填入的策略。

| 遇到的问题 | 优先检查 |
| --- | --- |
| 提供器加载失败 | 打开订阅 URL，确认文件有顶层 `payload:`。即使 URL 以 `.txt` 结尾，配置也应使用 `behavior: classical` 和 `format: yaml`。 |
| 连接走了其他策略 | 查看实际命中的规则。如果前面的规则截获了同一域名，把当前规则移到它前面。 |
| 没看到最近的规则变更 | 确认 URL 指向 `main`，再刷新对应规则集或提供器。 |

反馈时请附上客户端版本、域名、规则文件、实际命中的规则和预期策略。分享配置或日志前，去掉凭据和私有订阅地址。

## 维护规则

- `rules/` 和 `clash/` 下已发布的路径是订阅地址，应保持稳定。
- 调整覆盖范围时，对照两种客户端的规则，并同步更新中英文索引。修改 AI 服务时，也检查独立维护的 `AI.txt`。
- 私有订阅和生成的配置放在 `local/`。
- 修改屏蔽名单时记录来源和理由。[Reject 维护说明](rules.zh-Hans.md#reject-策略与来源)
