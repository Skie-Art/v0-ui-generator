# Changelog

All notable changes to the v0 UI Generator extension and standalone MCP package will be documented in this file.

## [2.0.0] - 2026-05-16

### Changed

- **v0 Platform API compatibility** — upgraded to the current `v0-sdk` 0.16.x line.
- **Current model IDs** — `v0_generate_ui` and `v0_refine_ui` now expose `v0-auto`, `v0-mini`, `v0-pro`, `v0-max`, and `v0-max-fast`.
- **Default model behavior** — omitting `model` now lets v0 choose the default model instead of sending a hardcoded default.
- **Refinement API** — migrated refinement calls to the current `v0.chats.sendMessage()` SDK method.
- **Response normalization** — generation/refinement responses preserve MCP-facing fields while handling current `webUrl` and `latestVersion.files` response shapes.
- **Product positioning** — updated package and README copy to describe both distribution paths: the VS Code extension for MCP-aware VS Code assistants and the standalone npm MCP server for MCP-compatible IDEs, CLIs, and agent runtimes. Claude Code remains a supported example.

### Fixed

- Removed stale `v0-1.5-*` model IDs that are no longer accepted by the v0 Platform API.
- Added lightweight tool-argument validation so missing required values fail clearly instead of being sent as literal `"undefined"` strings.

## [1.0.4] - 2026-04-06 (Preview)

### Added

- **npm package** — standalone MCP server published to npm as `v0-ui-generator`. Claude Code users can set up with a single command: `claude mcp add v0-ui-generator -e V0_API_KEY=key -- npx v0-ui-generator`
- **npm badge** on the overview page

### Changed

- **Claude Code setup** — simplified from finding the extension install path to a one-liner using npx

## [1.0.0] - 2026-04-05 (Preview)

First public release — free during preview.

### Added

- **Marketplace overview** — rewrote the extension page with use cases, workflow examples, and visual documentation (hero image, GIF walkthroughs, design consultation screenshots)
- **Badges** — VS Code Marketplace version, install count, and license badges on the overview page

### Changed

- **Display name** — now "v0 UI Generator (Preview)" to signal free preview period
- **Description** — rewritten to lead with what the extension does for your workflow, not just what it is
- **Getting started** — streamlined setup instructions for both VS Code and Claude Code
- **Tool reference** — reorganized the 12 MCP tools into grouped categories (generation, extraction, chat management, projects, operations)

### Fixed (0.1.1–0.1.3)

- Extension activation failure caused by `type: module` in package.json ([0.1.2])
- Walkthrough panels showing raw text instead of rendered markdown ([0.1.1])
- Claude Code setup docs now clarify that `V0_API_KEY` must be set as an environment variable separately from VS Code SecretStorage ([0.1.3])

## [0.1.0] - 2026-03-27 (Pre-release)

### Added

- 12 MCP tools for the Vercel v0 Platform API
  - **Generate UI** from text prompts (`v0_generate_ui`)
  - **Refine UI** with follow-up messages (`v0_refine_ui`)
  - **Chat management** — get, list, track active chats
  - **Project management** — create, list, assign chats to projects
  - **Deployment diagnostics** — check logs and errors
  - **Setup check** — validate API connectivity and account info
- Secure API key storage via VS Code SecretStorage
- Status bar indicator showing connection state
- Getting started walkthrough for first-time setup
