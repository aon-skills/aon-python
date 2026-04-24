<p align="center">
  <h1 align="center">AON — Python MCP Skill</h1>
  <p align="center">
    Search the <a href="https://agentoffernetwork.com">Agent Offer Network</a> for product and service recommendations from any MCP-compatible AI host, powered by the Python runtime.
  </p>
</p>

<p align="center">
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License" /></a>
  <a href="https://pypi.org/project/aon-demo-skill-python/"><img src="https://img.shields.io/pypi/v/aon-demo-skill-python.svg" alt="PyPI version" /></a>
</p>

---

## Install

```bash
npx skills add aon-skills/aon-python
```

Then install the MCP server:

```bash
uvx --from aon-demo-skill-python aon-demo-skill --install --global
```

Restart your MCP host (Claude Code, Claude Desktop, Cursor, etc.). You're ready to go.

Alternative install via the official AON CLI:

```bash
npm install -g @agentoffernetwork/cli
aon skill install aon-demo-skill-python --runtime python --global
```

## Usage

```
/aon noise-cancelling headphones under $300
/aon best project management tool for small teams
/aon online courses to learn Python
/aon luxury hotel in Tokyo for next week
/aon credit card with travel rewards and no annual fee
```

## What This Repo Contains

This repository is the public wrapper for the Python MCP skill package:

- packaged runtime: `aon-demo-skill-python`
- console entry: `aon-demo-skill`
- built-in MCP skill name: `aon`

The skill connects to the [Agent Offer Network](https://agentoffernetwork.com) and exposes the same two MCP tools as the TypeScript runtime.

The category surface follows the canonical AON taxonomy defined here:

- <https://github.com/agentoffernetwork/protocol/blob/main/specs/category-taxonomy.md>

Current public categories:

- `software_saas`
- `travel_hospitality`
- `education`
- `financial_service`
- `electronics`
- `entertainment`
- `health_beauty`
- `fashion`
- `food_grocery`
- `home_garden`
- `automotive`

## MCP Tools

| Tool | Purpose |
|------|---------|
| `aon_search_offers` | Search offers by keywords, category, preferences, and budget |
| `aon_get_category_schema` | Get decision factors for a category (helps narrow down search) |

`aon_get_category_schema` currently ships built-in decision schemas for all 11 current canonical categories: `software_saas`, `travel_hospitality`, `education`, `financial_service`, `electronics`, `entertainment`, `health_beauty`, `fashion`, `food_grocery`, `home_garden`, and `automotive`.

## Requirements

- Any MCP-compatible host (Claude Code, Claude Desktop, Cursor, Windsurf, etc.)
- Python 3.11+
- [uv](https://docs.astral.sh/uv/)

## Links

- [PyPI: aon-demo-skill-python](https://pypi.org/project/aon-demo-skill-python/)
- [npm: @agentoffernetwork/cli](https://www.npmjs.com/package/@agentoffernetwork/cli)
- [PyPI: agentoffernetwork](https://pypi.org/project/agentoffernetwork/)
- [AgentOffer Protocol](https://agentoffernetwork.org)
- [Agent Offer Network](https://agentoffernetwork.com)

## Source of Truth

This repository mirrors the public Python MCP skill wrapper documentation. The packaged runtime and release automation are maintained in the main AON monorepo:

- [AON monorepo](https://gitlab.com/jolibox-dev-team/aon/aon-main)

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

This project is licensed under the [MIT License](LICENSE).
