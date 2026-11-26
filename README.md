# petclinic-plugins

Agent plugins shared by every petclinic service. One repository is a marketplace for both
**Claude Code** (`.claude-plugin/marketplace.json`) and **GitHub Copilot CLI**
(`.github/plugin/marketplace.json`); each plugin's `.claude-plugin/plugin.json` is read by both.

| Plugin | What it does | Use |
| --- | --- | --- |
| `grill-me` | Interviews you relentlessly about a plan, one question at a time, until you share an understanding | `/grill-me <plan>` |

## Install

| Harness | Commands |
| --- | --- |
| Claude Code | `/plugin marketplace add victorrentea/petclinic-plugins`<br>`/plugin install grill-me@petclinic-plugins` |
| Copilot CLI | `copilot plugin marketplace add victorrentea/petclinic-plugins`<br>`copilot plugin install grill-me@petclinic-plugins` |

If the short name clashes with another skill, call it by its full name: `/grill-me:grill-me`.

## Adding a plugin

1. `plugins/<name>/.claude-plugin/plugin.json` plus `plugins/<name>/skills/<skill>/SKILL.md`.
2. List it in **both** marketplace files — they must stay identical.
3. No `version` field anywhere: without one, each push (a new commit SHA) is a new version,
   so installs pick it up on the next update.
