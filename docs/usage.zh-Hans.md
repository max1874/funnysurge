# 配置指南

[首页](../README.zh-Hans.md) · [规则索引](rules.md) · [English](usage.md)

## Surge 规则集

1. 在[规则索引](rules.md)中选择需要的名单，复制 Surge 对应的原始链接。
2. 在已有的 `[Rule]` 段内添加 `RULE-SET,<raw-url>,<policy>`。策略名应是配置中已经存在的节点或策略组，或者你有意选择的 `DIRECT`、`REJECT` 等内置策略。
3. 把具体规则放在可能先匹配同一请求的宽泛规则之前，并排在 `FINAL` 之前。保存配置，在客户端更新规则集。
4. 打开对应服务，在请求记录中查看实际命中的规则与最终策略。

[示例片段](../examples/surge-rules.conf)包含 OpenAI、Anthropic 和 Gemini。复制条目到现有配置段中，不要重复添加 `[Rule]` 段。需要统一分流多个服务时可选择 `AI.txt`；需要分别指定策略时用独立名单。如果两者都用，应把具体服务的覆盖规则放在前面。

匹配行为参考 Surge 的[规则系统文档](https://manual.nssurge.com/rules/overview.html)。

## Clash / Mihomo rule-provider

使用 `clash/` 下的文件，设置 `behavior: classical` 和 `format: yaml`。为兼容已有订阅，扩展名保留 `.txt`，文件内容实际是 YAML `payload` 列表。

把[示例片段](../examples/clash-rule-providers.yaml)合并进当前配置。顶层保留一个 `rule-providers` 映射和一个 `rules` 列表，向它们追加内容，不要重复创建同名 YAML 键。每个 provider 使用独立的名称和缓存路径。将 `PROXY` 替换成已有策略名。

把 `RULE-SET` 条目排在宽泛匹配和 `MATCH` 之前。重新加载配置、更新 provider，再查看连接记录。示例的更新间隔是 86,400 秒，也可以手动提前刷新。参数含义见 [Mihomo 官方文档](https://wiki.metacubex.one/config/rule-providers/)。

## 使用 Surge 基础配置

[`base.conf`](../base.conf) 是个人配置的起点。它没有 `[Proxy]` 段，`include-other-group=` 也留空，使用前需要接入节点来源。地区策略组使用 `smart`，要求 Surge iOS 5.11.0 / Mac 5.7.0 或更新版本；见 [Smart Group 文档](https://manual.nssurge.com/policy-groups/smart.html)。

1. 将 `base.conf` 另存为私有副本。如果在克隆的仓库里操作，把副本和凭据放进已忽略的 `local/` 目录。
2. 在 `[Proxy Group]` 段添加节点来源组，填写你自己的 Surge 格式订阅。例如，替换下面的占位 URL：

   ```ini
   Subscription = select, policy-path=https://example.com/your-surge-subscription
   ```

3. 把**所有**空的 `include-other-group=` 改成 `include-other-group=Subscription`，包括 `PROXY` 和六个地区组。来源组名称需保持一致。Surge 支持节点列表，或带 `[Proxy]` 段的完整 Surge 配置作为来源，不能直接换成任意 Clash 订阅。详见 [Policy Including](https://manual.nssurge.com/policy-groups/policy-including.html)。
4. 对照自己的节点名称检查地区正则。某地区没有匹配节点时，调整筛选条件或相应的策略组引用。AI 和媒体组也引用这些地区组，选中的路径必须能找到可用节点。
5. 检查下表中的默认行为，再导入私有副本。在自己的客户端查看规则命中与所选策略后再正式使用。

| `base.conf` 中的默认行为 | 需要检查什么 |
| --- | --- |
| 使用大陆 DNS，禁用 IPv6 | 是否符合当前网络环境 |
| 开启局域网代理访问；HTTP `6152`、SOCKS5 `6153` | 是否需要其他局域网设备使用此代理 |
| AI、媒体和地区策略组 | 节点是否可用，各服务应走哪个地区 |
| Brokerage 和 DDNS 直连 | 直连是否适合自己的环境 |
| 个人 Reject 名单与第三方 Reject 名单 | 阅读[个人名单的范围和来源](reject.md)；不需要时从副本中移除对应 `RULE-SET` 行 |
| 第三方远程规则订阅 | 地址是否可访问，以及独立变化的覆盖范围 |

基础配置使用 Sukka 的 AI 规则加本地补充，并未直接订阅本仓库的 `AI.txt`。按需添加独立名单与使用整份基础配置是两种接入方式。

## 更新与排查

示例中的原始链接跟随 `main`。上游修改进入该分支后，需要在客户端刷新对应规则集或 provider。如果修改的是 `base.conf`，还需要更新自己的配置；只刷新规则集不会更新策略组或设置。

| 现象 | 优先检查 |
| --- | --- |
| 名单已下载，但流量走错策略 | 是否有更早命中的规则、目标策略组是否正确、客户端是否处于规则模式 |
| Provider 格式错误 | Surge 使用 `rules/`；Clash / Mihomo 使用 `clash/` 和 `classical` / `yaml` |
| 基础配置中的地区组为空 | 来源组、`include-other-group` 和节点名称正则 |
| 网站意外被拦截 | 实际命中的 Reject 规则；个人名单包含 CSDN 和博客园 |
| 修改尚未生效 | URL 所指分支、客户端缓存，以及修改的是规则还是配置本身 |

反馈问题时，附上域名、客户端版本、规则文件、命中的规则和期望策略。分享配置或日志前，移除订阅 URL、token 和节点凭据。

## 维护规则

- 保持公开 `.txt` 文件的路径稳定，它们直接作为原始订阅地址使用。
- 修改共享覆盖范围时，对照两种客户端格式。它们是手动维护的，存在[已知差异](rules.md#coverage-notes--覆盖说明)；修改 AI 服务时也应考虑独立维护的 `AI.txt` 聚合名单。
- 新增名单或改变格式覆盖情况时，更新规则索引。
- 修改 Reject 时同步两份名单，并在 [reject.md](reject.md) 中记录来源、理由、数量和日期。
- 私有订阅与生成的个人配置保存在 `local/`。
- 首页与配置指南的两种语言版本保持同步。
