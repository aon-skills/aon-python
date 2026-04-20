# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/), and this project adheres to [Semantic Versioning](https://semver.org/).

## [Unreleased]

### Added

- Add the public GitHub wrapper repository source for the Python MCP skill
- Add release-note categories and public governance templates for the Python skill repo
- Add GitHub Actions workflows to validate the public wrapper surface and manually publish GitHub Releases

## [0.1.0] - 2026-04-20

### Changed

- First public Python MCP skill release aligned with the `agentoffernetwork` 0.1.0 SDK surface
- Support zero-config install via `uvx --from aon-demo-skill-python aon-demo-skill --install --global`
- Expose packaged `SKILL.md` content so AON CLI can install the Python skill instructions directly from the published artifact