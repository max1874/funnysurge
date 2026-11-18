<div align="center">
  <img src="assets/icon.svg" width="160" alt="funnysurge routing icon">
  <h1>funnysurge</h1>
  <p><a href="docs/rules.md">Rule catalog</a> · <a href="docs/usage.md">Setup guide</a> · <a href="README.zh-Hans.md">简体中文</a></p>
</div>

Hand-maintained routing rules for Surge and Clash / Mihomo. Choose a list for an AI service, developer tool, media service, or site you want to block, then assign it a policy in your existing client configuration. Bring your own proxy nodes.

## Get started

1. Find the list you want and copy the link for your client. [Rule catalog](docs/rules.md)
2. Add the rule to your profile. The guide has copyable examples and shows how to check which policy matched. [Surge](docs/usage.md#surge) · [Clash / Mihomo](docs/usage.md#clash--mihomo)

Use `AI.txt` to route several AI services through one policy. Choose individual lists to route ChatGPT, Claude, or Gemini separately. If you use both, place the individual lists first. [Coverage notes](docs/rules.md#coverage-notes)

<p align="center">
  <a href="https://max1874.com/funnysurge/"><img src="assets/demo.en.webp" width="600" alt="Demo of domain rules selecting PROXY, DIRECT, or REJECT"></a>
  <br>
  <sub><a href="https://max1874.com/funnysurge/">Try the routing demo</a></sub>
</p>

The rule links follow `main`. Refresh the rule set in your client to pick up changes. To report a missing or misrouted domain, include the client, domain, matched rule, and intended policy. [Open an issue](https://github.com/max1874/funnysurge/issues)

[MIT](LICENSE) © 2024 MAX LIN. Original copyright notices are preserved.
