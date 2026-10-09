# IBKR / Interactive Brokers · 盈透证券

独立维护的域名规则集，Surge 与 Clash / Mihomo 两份名单保持一致。
首次整理及来源核对：2026-10-09。此日期表示核对名单，不代表已逐个验证域名或实测交易连接。

## 使用

在 Surge 的 `[Rule]` 中添加，放在宽泛规则和 `FINAL` 之前：

```ini
RULE-SET,https://raw.githubusercontent.com/max1874/funnysurge/main/rules/IBKR.txt,PROXY
```

把 `PROXY` 替换为实际节点或策略组。Clash 示例见
[配置片段](../examples/clash-rule-providers.yaml)。基础配置中的
`Brokerage.txt` 用于富途 / moomoo；IBKR 单独订阅、单独选策略。

## 来源与覆盖

- [v2fly/domain-list-community 的 ibkr 名单](https://github.com/v2fly/domain-list-community/blob/master/data/ibkr)：21 个核心及地区域名。
- [GravityPoet 的 IBKR.list](https://gist.github.com/GravityPoet/4b67598168e7b4b4a222f130405458e1)：补充 `ibllc.com.cn`、`ibkr.info`、`ibkr.hk`、`interactivebrokers.com.cn`、`ibkr.com.cn`。这些属于社区收录，未独立验证每个域名的现有用途。
- 2026-10-09 用户提供的 Surge 截图：观察到 `api.ibkr.com`、`sdc1-hb1.ibllc.com`、`sdc1-hb2.ibllc.com`、`sdc1.ibllc.com`、`hdc1.ibllc.com`、`download2.interactivebrokers.com`，均由后缀规则覆盖。

共 26 条去重的 `DOMAIN-SUFFIX` 规则，覆盖相应根域名及子域名。
`api.ibkr.com` 已由 `ibkr.com` 覆盖，无需重复添加。
名单涵盖已收录的 Gateway / TWS 基础设施、API、官网、地区入口和指南，
不保证覆盖全部 IBKR 流量，尤其是纯 IP 连接或第三方服务。
不按关键词扩大匹配，也不按 4000 / 4001 等端口匹配所有应用。

## Mac 进程补充

截图中的 Gateway 可执行文件名是 `JavaApplicationStub`，但其他 Java 应用也可能使用此名称，
因此公共名单不包含这个通用进程名。
需要覆盖 Gateway 的纯 IP 连接时，在本机查看 Surge 请求详情的进程路径，
按真实路径添加 `PROCESS-NAME` 规则。不要从应用显示名称猜测安装路径。

Surge Mac 6.0+ 支持以 `/` 开头并结尾的应用目录前缀匹配；也支持可执行文件完整路径。
具体语法见 [Surge 官方进程规则说明](https://manual.nssurge.com/rules/process.html)。

## 维护流程

1. 在登录、连接 Gateway / TWS、行情订阅、账户管理、软件下载等实际操作后查看 Surge 请求记录。
2. 对未命中的连接记录域名、应用、用途及期望策略；提交记录时去掉账号、Cookie、令牌和 URL 查询参数。
3. 核实域名用途后，优先添加适当的后缀规则；共享第三方基础设施仅添加有证据的精确主机名。
4. 同时更新 `rules/IBKR.txt` 和 `clash/IBKR.txt`，记录新增来源及核对日期，检查重复和后缀包含关系。
5. 刷新规则集并新建连接，确认实际命中规则及最终策略。已有长连接可能需要重新连接才能验证。

仅执行 DNS 解析不能证明域名属于 IBKR，也不能证明规则完整。
这是一份手工维护的名单，没有自动发现域名或定时更新任务。
