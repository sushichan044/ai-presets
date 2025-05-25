# ai-presets
My presets for AI Agents. Can be installed via [ajisai](https://github.com/sushichan044/ajisai).

```yaml
workspace:
  imports:
    sushichan044:
      type: git
      repository: https://github.com/sushichan044/ai-presets.git
      include:
        - essentials
        - tdd
        - typescript
  integrations:
    cursor:
      enabled: true
    github-copilot:
      enabled: true
```
