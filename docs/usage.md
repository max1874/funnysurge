# Setup guide

[Home](../README.md) · [Rule catalog](rules.md) · [简体中文](usage.zh-Hans.md)

## Surge rule sets

1. Choose a list from the [catalog](rules.md) and copy its Surge raw URL.
2. Add `RULE-SET,<raw-url>,<policy>` inside your existing `[Rule]` section. Use
   the name of a proxy or group already defined in your profile, or an intended
   built-in policy such as `DIRECT` or `REJECT`.
3. Place specific rules before broader rules that would otherwise match the
   same request, and before `FINAL`. Save and refresh the rule set in the client.
4. Open the service, then inspect the request's matched rule and final policy.

[Copyable Surge example](../README.md#surge) · [Surge rule matching](https://manual.nssurge.com/rules/overview.html)

## Clash / Mihomo rule providers

1. Copy the Clash / Mihomo raw URL from the [rule catalog](rules.md).
2. Add an entry to the existing top-level `rule-providers` mapping. Use
   `behavior: classical` and `format: yaml` for these YAML files with a `.txt`
   extension. Give each provider a unique name and cache path.
3. Add `RULE-SET,<provider-name>,<policy>` to the existing `rules` list before
   broader matches and `MATCH`. Choose a configured policy or a built-in one
   such as `DIRECT`.
4. Reload the profile, refresh the provider, then inspect a matching connection.

[Copyable Clash / Mihomo example](../README.md#clash--mihomo) · [Mihomo provider options](https://wiki.metacubex.one/en/config/rule-providers/)

## Updates and troubleshooting

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

## Maintaining rules

- Keep published `.txt` paths stable. They are consumed directly as raw URLs.
- Review both client versions when changing shared coverage. They are manually
  maintained and have [known differences](rules.md#coverage-notes--覆盖说明);
  also consider the separate `AI.txt` aggregate when editing an AI service.
- Add or update the catalog when introducing a list or changing format coverage.
- For Reject changes, update both lists and record the source, reason, count,
  and date. [Reject policy and sources](rules.md#reject-policy-and-sources--reject-策略与来源)
- Keep private subscriptions and generated personal profiles in `local/`.
- Update both languages when editing the overview, setup guide, or rule catalog.
