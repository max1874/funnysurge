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

For broader AI coverage, pick `AI.txt`. Use individual lists when services need
different policies. If you use both, put specific overrides first.
[Surge quick start](../README.md#surge)

See Surge's [rule system documentation](https://manual.nssurge.com/rules/overview.html)
for matching behavior.

## Clash / Mihomo rule providers

Use the files from `clash/`, with `behavior: classical` and `format: yaml`.
Their `.txt` extension is retained for existing subscribers; the content is a
YAML `payload` list.

Add provider definitions to the top-level `rule-providers` mapping and matching
entries to the `rules` list. Give each provider a unique name and cache path,
and replace `PROXY` with your own policy name.
[Clash / Mihomo quick start](../README.md#clash--mihomo)

Put `RULE-SET` entries before broader matches and `MATCH`. Reload the profile,
refresh the provider, then inspect a matching connection. The example requests
provider updates every 86,400 seconds; a manual refresh can fetch a new list
sooner. Provider options are documented in the
[Mihomo manual](https://wiki.metacubex.one/en/config/rule-providers/).

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
  and date in [reject.md](reject.md).
- Keep private subscriptions and generated personal profiles in `local/`.
- Keep both language versions of the overview and setup guide aligned.
