# wa-number-checker-skills

English | [中文](#中文)

Verify if a phone number is registered on WhatsApp. Use with Claude Code or Cursor.

**Repository:** [github.com/whatsabot-hq/wa-number-checker-skills](https://github.com/whatsabot-hq/wa-number-checker-skills)

## Prerequisites

- Access to the [WhatsApp Number Checker API](https://wa-check-api.whatsabot.com). You need an API key for REST or MCP calls (see [API docs](https://wa-check-api.whatsabot.com) or `Skills/references/api.md` in this repo).
- For Cursor: copy or symlink the `Skills` directory to `~/.cursor/skills/wa-number-checker-skills` so the skill is loaded.

## Installation

### Quick Install (Recommended)

```bash
npx skills add whatsabot-hq/wa-number-checker-skills
```

### Register as Plugin Marketplace (Claude Code)

In Claude Code, run:

```
/plugin marketplace add whatsabot-hq/wa-number-checker-skills
```

### Install the skill

**Option 1: Browse UI**

1. Select **Browse and install plugins**
2. Select **wa-number-checker-skills**
3. Select **wa-number-checker** and choose **Install now**

**Option 2: Direct install**

```
/plugin install wa-number-checker@wa-number-checker-skills
```

**Option 3: Ask the agent**

Tell Claude Code: “Please install Skills from github.com/whatsabot-hq/wa-number-checker-skills”

## Update Skills

To update to the latest version:

1. Run `/plugin` in Claude Code
2. Switch to the **Marketplaces** tab
3. Select **wa-number-checker-skills**
4. Choose **Update marketplace**

You can also **Enable auto-update** to get the latest versions automatically.

## Available Skills

| Skill               | Description                                              |
|---------------------|----------------------------------------------------------|
| **wa-number-checker** | Query whether a phone number is registered on WhatsApp. |

- **When to use**: User asks “Does this number have WhatsApp?”, “查这个号有没有 WhatsApp”, “WhatsApp number check”, etc.
- **How it works**: Prefer the wa-check-api MCP tool `check_whatsapp_number(phone)`; otherwise use the REST API (see `Skills/references/api.md`).
- **Parameter**: `phone` in E.164 or digits (e.g. `+34605797764`).
- **Example**: “Check +34605797764” or “Is 34605797764 on WhatsApp?”

## API and credentials

- **Get API key**: See [wa-check-api.whatsabot.com](https://wa-check-api.whatsabot.com) or `Skills/references/api.md` in this repo.
- **REST**: Send `x-api-key: YOUR_API_KEY` in the request header.
- **MCP**: Configure the wa-check-api MCP with the same API key (see your Claude Code or Cursor MCP settings).

## Repository structure

```
wa-number-checker-skills/
├── README.md           # This file
├── CLAUDE.md           # Package-level instructions for Claude
├── marketplace.json    # Plugin manifest for Claude Code
└── Skills/
    ├── SKILL.md        # Skill entry and usage
    └── references/
        └── api.md      # REST API reference
```

## License

MIT

---

## 中文

用于查询某个电话号码是否已注册 WhatsApp 的技能，可在 Claude Code 或 Cursor 中使用。

- **安装**：运行 `npx skills add whatsabot-hq/wa-number-checker-skills` 或在 Claude Code 中执行 `/plugin marketplace add whatsabot-hq/wa-number-checker-skills`，然后安装 **wa-number-checker** 插件。
- **使用**：对助手说“查一下 +34605797764 有没有 WhatsApp”或 “Does this number have WhatsApp?” 等即可触发；需配置 [WhatsApp Number Checker API](https://wa-check-api.whatsabot.com) 的 API key（REST 或 MCP）。
