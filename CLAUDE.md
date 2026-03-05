# wa-number-checker-skills

This package is a **WhatsApp Number Check** skill for Claude (and Cursor). It answers whether a given phone number is registered on WhatsApp.

## Skill entry

- **Skill root**: `Skills/` (this is the directory to use when installing or publishing).
- **Entry file**: `Skills/SKILL.md` — when to use the skill, how to call (MCP first, then REST), parameters, and error handling.

## How to use

1. **When to trigger**: The user asks to check if a number has WhatsApp, e.g. “Does +34605797764 have WhatsApp?”, “查这个号有没有 WhatsApp”, “WhatsApp number check”.
2. **Call path**: If the **wa-check-api** MCP is available, use `check_whatsapp_number(phone)`. Otherwise use the REST API: `GET /api/wa/check?phone=...` with header `x-api-key`; see `Skills/references/api.md` for base URL, parameters, and error codes.
3. **Parameter**: `phone` — E.164 or digits only (e.g. `+34605797764` or `34605797764`).
4. **Result**: Interpret `result.exist` (true/false) and report back; on non-zero `code`, use the error code table in `Skills/references/api.md` to explain and suggest checking API key or credits.

## Publishing

When publishing this package (e.g. to GitHub as whatsabot-hq/wa-number-checker-skills), the **skill root** is the `Skills/` directory: plugins should point at `./Skills` so that `SKILL.md` and `references/api.md` are found there.
