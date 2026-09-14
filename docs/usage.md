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

The [example](../examples/surge-rules.conf) includes OpenAI, Anthropic, and
Gemini. Copy the entries into your existing section rather than adding a second
`[Rule]` section. Pick `AI.txt` for broader coverage; use individual lists when
services need different policies. If you use both, put specific overrides first.

See Surge's [rule system documentation](https://manual.nssurge.com/rules/overview.html)
for matching behavior.

## Clash / Mihomo rule providers

Use the files from `clash/`, with `behavior: classical` and `format: yaml`.
Their `.txt` extension is retained for existing subscribers; the content is a
YAML `payload` list.

Merge the [example](../examples/clash-rule-providers.yaml) into your current
configuration. Keep one top-level `rule-providers` mapping and one `rules` list;
append entries under those keys instead of duplicating them. Give each provider
a unique name and cache path. Replace `PROXY` with your own policy name.

Put `RULE-SET` entries before broader matches and `MATCH`. Reload the profile,
refresh the provider, then inspect a matching connection. The example requests
provider updates every 86,400 seconds; a manual refresh can fetch a new list
sooner. Provider options are documented in the
[Mihomo manual](https://wiki.metacubex.one/en/config/rule-providers/).

## Use the Surge base profile

[`base.conf`](../base.conf) is a starting point for a personal setup. It has no
`[Proxy]` section and leaves `include-other-group=` empty, so it needs a proxy
source before use. Its regional groups use `smart`, supported from Surge iOS
5.11.0 / Mac 5.7.0; see the [Smart Group documentation](https://manual.nssurge.com/policy-groups/smart.html).

1. Save a private copy of `base.conf`. If working in a clone, put your copy and
   credentials under the ignored `local/` directory.
2. Add a source group inside `[Proxy Group]`, using your own Surge-compatible
   proxy subscription. For example, replace the placeholder URL here:

   ```ini
   Subscription = select, policy-path=https://example.com/your-surge-subscription
   ```

3. Fill **every** empty `include-other-group=` with `include-other-group=Subscription`,
   including the `PROXY` group and all six regional groups. Use the same source
   group name throughout. Surge supports policy lists or complete profiles
   with a `[Proxy]` section as a source; an arbitrary Clash subscription is not
   interchangeable. See [Policy Including](https://manual.nssurge.com/policy-groups/policy-including.html).
4. Check the regional name filters against your nodes. Change filters or group
   references where a region has no matching node. The AI and media groups refer
   to those regions, so their selected paths must also resolve to usable proxies.
5. Review the defaults below, then import the private copy. Inspect rule hits
   and selected policies in your own client before relying on the profile.

| Default in `base.conf` | What to review |
| --- | --- |
| Mainland DNS resolvers; IPv6 disabled | Whether those choices fit your network |
| LAN proxy access enabled; HTTP `6152`, SOCKS5 `6153` | Whether you want other LAN devices to use this proxy |
| AI, media, and regional policy groups | Available nodes and the region you want each service to use |
| Brokerage and DDNS use `DIRECT` | Whether direct access is appropriate for your setup |
| Personal Reject list plus a third-party Reject list | The [personal list's scope and sources](reject.md); remove its `RULE-SET` line from your copy if unwanted |
| External rule subscriptions | Their reachability and independently changing coverage |

The base profile uses Sukka's AI rules plus local additions; it does not simply
subscribe to this repository's `AI.txt`. Choosing individual lists and adapting
the full profile are separate setup options.

## Updates and troubleshooting

Raw links in the examples follow `main`. After an upstream change reaches that
branch, refresh the relevant rule set or provider in the client. Changes to
`base.conf` also require updating your own profile; refreshing rules alone will
not update its policy groups or settings.

| Symptom | Inspect first |
| --- | --- |
| List downloaded, but traffic uses the wrong policy | Earlier matching rules, the target group, and the client's rule mode |
| Provider format error | Use `rules/` for Surge, `clash/` with `classical` / `yaml` for Clash / Mihomo |
| Empty regional group in the base profile | The source group, `include-other-group`, and node-name regex filters |
| A site is unexpectedly blocked | The matched Reject rule; the personal list includes CSDN and cnblogs |
| A change has not appeared | The URL's branch, the client's cached list, and whether the change is to rules or the profile itself |

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
