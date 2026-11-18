# Setup guide

[Overview](../README.md) · [Rule catalog](rules.md) · [简体中文](usage.zh-Hans.md)

Start with a working profile. Replace `PROXY` in the examples with a proxy or policy group you already use.

## Surge

Add this line to your existing `[Rule]` section, above any broader matching rule and `FINAL`.

```ini
RULE-SET,https://raw.githubusercontent.com/max1874/funnysurge/main/rules/OpenAI.txt,PROXY
```

Save the profile and refresh the rule set. For another service, replace the URL with its **Surge** link. [Rule catalog](rules.md) · [Surge rule set reference](https://manual.nssurge.com/rules/ruleset.html)

## Clash / Mihomo

Add `funnysurge-openai` under `rule-providers` and the `RULE-SET` line to `rules`. Merge into any existing keys and put the rule above broader matches and `MATCH`.

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

Reload the profile and refresh the provider. For another service, use its **Clash / Mihomo** link and give the new provider its own name and cache path. The provider name must match the name in the `RULE-SET` line. [Rule catalog](rules.md) · [Mihomo provider reference](https://wiki.metacubex.one/en/config/rule-providers/)

<a name="updates-and-troubleshooting"></a>

## Check the match

Use rule mode and open `chatgpt.com`. Look for a new connection to that domain in the client. The matched rule should point to the OpenAI list and use the policy you entered.

| If you see | Check |
| --- | --- |
| The provider fails to load | Open its URL. The Clash / Mihomo file has a top-level `payload:` key. In the profile, use `behavior: classical` and `format: yaml` even though the URL ends in `.txt`. |
| The connection uses another policy | Check which rule matched. Move this rule above any earlier match for the same domain. |
| A recent change is missing | Make sure the URL points to `main`, then refresh the list or provider. |

When reporting an issue, include the client version, domain, rule file, matched rule, and expected policy. Remove credentials and private subscription URLs from what you share.

## Maintaining rules

- Published `rules/` and `clash/` paths are subscription URLs. Keep them stable.
- For a coverage change, review both client formats and update the catalog in both languages. For an AI service, also check the separate `AI.txt` list.
- Keep private subscriptions and generated profiles in `local/`.
- For blocklist changes, document the source and reason. [Reject maintenance notes](rules.md#reject-policy-and-sources)
