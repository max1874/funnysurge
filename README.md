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

funnysurge is my collection of routing rules for Surge and Clash / Mihomo,
covering AI services, development tools, media, direct connections, and sites I
choose to block. Subscribe to the lists you need and assign your own policies.

The repository also includes a personal Surge base profile. Bring your own
proxies: this project supplies rules and configuration examples, with no nodes
or subscription service.

## Pick what you need

| I want to… | Start here |
| --- | --- |
| Route ChatGPT, Claude, Gemini, or another service | [Rule catalog](docs/rules.md), with raw links for each client |
| Add rules to an existing Surge profile | [Surge snippet](examples/surge-rules.conf) |
| Add rule providers to Clash / Mihomo | [YAML snippet](examples/clash-rule-providers.yaml) |
| Adapt the full Surge base profile | [base.conf](base.conf) and its [setup guide](docs/usage.md#use-the-surge-base-profile) |
| Understand the personal blocklist | [Reject policy and sources · 中文](docs/reject.md) |

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
to see which rule and policy it actually used. More lists and optional direct
and reject rules are in the [Surge snippet](examples/surge-rules.conf).

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
├── base.conf                  Surge base profile; customize before use
├── rules/                     Surge rule sets (.txt)
├── clash/                     Clash / Mihomo classical providers (.txt, YAML)
├── examples/                  Snippets to merge into an existing profile
├── docs/                      Rule catalog, setup guides, Reject sources
├── assets/                    Project icon
└── LICENSE                    MIT
```

`rules/`, `clash/`, and `base.conf` keep their published paths so existing raw
subscriptions continue to work. Browse by service through the catalog, or by
client through the two rule directories.

## Scope and maintenance

- **Personal, manually curated coverage.** Lists reflect my setup and may need
  adjustment for yours. Some entries match shared infrastructure or broad
  keywords; service labels do not mean every match belongs only to that service.
- **Choose an aggregate or individual lists.** `AI.txt` combines several
  services and some additional domains. It is maintained separately, rather
  than generated as an exact union of the individual files.
- **The client formats have differences.** There are 20 Surge lists and 19
  Clash lists; TikTok is currently Surge-only. Same-name lists can differ in
  coverage. The [catalog](docs/rules.md) records the known differences.
- **Reject expresses a preference.** It includes sites such as CSDN and
  cnblogs. It blocks connections, not search results, and is not a malware
  classification. Read the [policy and sources](docs/reject.md) before enabling it.

For a correction, include the affected domain, client, rule file, and expected
route in an [issue](https://github.com/max1874/funnysurge/issues). See the
[maintenance notes](docs/usage.md#maintaining-rules) before editing a list.

## Sources and license

The base profile also references independently maintained rules from
[Sukka](https://github.com/SukkaW/Surge),
[blackmatrix7](https://github.com/blackmatrix7/ios_rule_script), and
[Loyalsoldier](https://github.com/Loyalsoldier/surge-rules). Those remote lists
have their own policies and licenses.

This repository is licensed under [MIT](LICENSE) © 2024 MAX LIN. Original copyright notices
are preserved.
