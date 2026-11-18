<div align="center">
  <img src="assets/icon.svg" width="160" alt="funnysurge routing icon">
  <h1>funnysurge</h1>
  <p><strong>Personal rules. Deliberate routes.</strong></p>
  <p>
    <img alt="Surge rule sets" src="https://img.shields.io/badge/Surge-rule%20sets-38BDF8">
    <img alt="Clash / Mihomo classical providers" src="https://img.shields.io/badge/Clash%20%2F%20Mihomo-classical-818CF8">
    <img alt="Manually maintained" src="https://img.shields.io/badge/maintenance-manual-FB923C">
    <a href="LICENSE"><img alt="MIT License" src="https://img.shields.io/badge/license-MIT-22C55E"></a>
  </p>
  <p><a href="#quick-start"><strong>Quick start</strong></a> · <a href="docs/rules.md">Rule catalog</a> · <a href="docs/usage.md">Setup guide</a> · <a href="README.zh-Hans.md">简体中文</a></p>
</div>

funnysurge is a set of hand-maintained routing rule sets for Surge and Clash / Mihomo.
The lists cover AI services, development tools, media, direct connections, and
sites I choose to block. Subscribe to the lists you need and assign your own policies.

<p align="center">
  <a href="https://max1874.com/funnysurge/"><img src="assets/demo.en.webp" width="600" alt="Domains go to PROXY, DIRECT or REJECT according to the list they are in"></a>
  <br>
  <sub>A recorded demo from <a href="https://max1874.com/funnysurge/">max1874.com/funnysurge</a>, where you can try it yourself.</sub>
</p>

## Pick what you need

| I want to… | Start here |
| --- | --- |
| Route ChatGPT, Claude, Gemini, or another service | [Rule catalog](docs/rules.md), with raw links for each client |
| Add rules to an existing Surge profile | [Surge quick start](#surge) |
| Add rule providers to Clash / Mihomo | [Clash / Mihomo quick start](#clash--mihomo) |
| Understand the personal blocklist | [Reject policy and sources · 中文](docs/rules.md#reject-策略与来源) |

## Quick start

Start with a working client configuration and a proxy or policy group of your
own. The examples below use `PROXY`; replace it with your existing policy name.

### Surge

Add this line inside your existing `[Rule]` section, before broader matching
rules and `FINAL`:

```ini
RULE-SET,https://raw.githubusercontent.com/max1874/funnysurge/main/rules/OpenAI.txt,PROXY
```

Save the profile, refresh the rule set, and inspect a matching request in Surge
to see which rule and policy it actually used. Find more lists, including direct
and reject rules, in the [rule catalog](docs/rules.md).

### Clash / Mihomo

Merge this provider into `rule-providers` and its rule into `rules`. Place the
rule before broader matches and `MATCH`; keep your existing proxies and groups.

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

These `.txt` files contain YAML `payload` lists. Use `behavior: classical` and
`format: yaml`. See the [setup guide](docs/usage.md) for merging, updates, and
troubleshooting.

## What's inside

```text
funnysurge/
├── README.md                  English overview
├── README.zh-Hans.md          中文说明
├── rules/                     Surge rule sets (.txt)
├── clash/                     Clash / Mihomo classical providers (.txt, YAML)
├── docs/                      Rule catalog, setup guides, and coverage notes
├── assets/                    Project icon and README demos
└── LICENSE                    MIT
```

`rules/` and `clash/` keep their published paths so existing raw
subscriptions continue to work. Browse by service through the catalog, or by
client through the two rule directories.

## FAQ

### Does this include proxy servers or a subscription?

No. A rule selects the policy for a connection. Supply the proxies in your
client configuration.

### Should I use `AI.txt` or the individual service lists?

Use `AI.txt` when every AI service should take the same policy. Use the
individual lists when services need different policies, and put them before
`AI.txt` if you use both.

### Does it work with Clash Verge Rev?

Clash Verge Rev runs the Mihomo core, so use the `clash/` files as
`behavior: classical`, `format: yaml` rule providers, as in the
[Clash / Mihomo quick start](#clash--mihomo).

### How are the lists updated?

By hand, with no generator, CI, or scheduled sync. Raw links follow `main`;
refresh the rule set or provider in your client to pick up changes.

### How does this relate to Sukka, blackmatrix7, or Loyalsoldier rules?

Those cover far more ground. These lists are small and specific, and you can
combine them with those projects' rules in your client.

More on the project page: <https://max1874.com/funnysurge/>

## Scope and maintenance

- **Personal, manually curated coverage.** Lists reflect my setup and may need
  adjustment for yours. Some entries match shared infrastructure or broad
  keywords; service labels do not mean every match belongs only to that service.
- **Choose an aggregate or individual lists.** `AI.txt` combines several
  services and some additional domains. It is maintained separately, rather
  than generated as an exact union of the individual files.
- **The client formats have differences.** There are 21 Surge lists and 20
  Clash lists; TikTok is currently Surge-only. Same-name lists can differ in
  coverage. The [catalog](docs/rules.md) records the known differences.
- **Reject expresses a preference.** It includes sites such as CSDN and
  cnblogs. It blocks connections, not search results, and is not a malware
  classification. Read the [policy and sources](docs/rules.md#reject-策略与来源) before enabling it.

For a correction, include the affected domain, client, rule file, and expected
route in an [issue](https://github.com/max1874/funnysurge/issues). See the
[maintenance notes](docs/usage.md#maintaining-rules) before editing a list.

## License

This repository is licensed under [MIT](LICENSE) © 2024 MAX LIN. Original copyright notices
are preserved.
