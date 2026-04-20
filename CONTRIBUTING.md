# Contributing

Thanks for your interest in improving the AON Python skill.

## Scope

This repository contains the Claude Code skill definition and public wrapper documentation for the AON Python MCP skill. The packaged runtime and release automation live in the main [AON monorepo](https://gitlab.com/jolibox-dev-team/aon/aon-main).

## Where to Send Changes

- **SKILL.md improvements** (better prompts, tool usage guidance): pull request
- **README updates** (clearer docs, new examples): pull request
- **Bug reports** (skill not working, wrong results): [open an issue](https://github.com/aon-skills/aon-python/issues)
- **Feature requests** (new categories, new tools): [open an issue](https://github.com/aon-skills/aon-python/issues)

## Development

The packaged skill file (`SKILL.md`) mirrors the Python MCP runtime behavior. To test changes locally:

1. Edit `SKILL.md` or the monorepo source file
2. Copy it to your Claude Code skills directory: `~/.claude/skills/aon/SKILL.md`
3. Restart Claude Code
4. Test with `/aon <query>`

## Code of Conduct

By participating in this project, you agree to follow our [Code of Conduct](CODE_OF_CONDUCT.md).