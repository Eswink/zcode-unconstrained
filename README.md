# zcode-unconstrained

ZCode marketplace repository for a provider-agnostic execution plugin.

The plugin injects a direct execution contract through `SessionStart` and `UserPromptSubmit` hooks. The hook emits only `additionalContext`, which is the recognized ZCode hook output field.

## Layout

```text
marketplace.json
zcode-unconstrained/
  .zcode-plugin/plugin.json
  hooks/hooks.json
  scripts/override.mjs
  skills/unconstrained-execution/SKILL.md
```

## Install in ZCode

Add this GitHub repository as a marketplace, then enable `zcode-unconstrained`.

Do not set `hooks` in `plugin.json` when the plugin uses the default `hooks/hooks.json` path; ZCode already loads that default path, and declaring the same path again creates a duplicate-file warning.

## Validate

```powershell
node "D:\development\ZCode\resources\glm\packages\plugin-creator-plugin\skills\plugin-creator\scripts\validate-plugin.mjs" "zcode-unconstrained"
node "zcode-unconstrained\scripts\override.mjs"
```
