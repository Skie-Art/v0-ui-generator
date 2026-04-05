[![VS Code Marketplace](https://img.shields.io/visual-studio-marketplace/v/skie-art.v0-ui-generator?label=VS%20Code%20Marketplace&color=blue)](https://marketplace.visualstudio.com/items?itemName=skie-art.v0-ui-generator)
[![Installs](https://img.shields.io/visual-studio-marketplace/i/skie-art.v0-ui-generator)](https://marketplace.visualstudio.com/items?itemName=skie-art.v0-ui-generator)
[![npm](https://img.shields.io/npm/v/v0-ui-generator?label=npm&color=cb3837)](https://www.npmjs.com/package/v0-ui-generator)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Built with ☕, 🐈‍⬛, and far too many oklch values.

# v0 UI Generator

**Bring a design specialist to your project.**

Generate, iterate, and consult on UI right in your editor — using your favourite AI assistant, powered by [v0](https://v0.app), delivered through [MCP](https://modelcontextprotocol.io).

---

<img src="https://raw.githubusercontent.com/Skie-Art/v0-ui-generator/main/assets/screenshots/hero.png" alt="v0 UI Generator in action" width="670" />

---

## What this does

Your AI coding assistant is great at logic, architecture, and implementation. It's not great at visual design. v0 is.

This extension connects [v0](https://v0.app) to **Claude Code**, **GitHub Copilot**, and any MCP-compatible agent — so your assistant can generate components, consult on design decisions, and iterate on UI without leaving your editor. No tab-switching, no copy-pasting — v0's design expertise becomes part of your assistant's toolkit through 12 MCP tools.

### ⚇ &nbsp; _Agent in the loop_

The real power is in how your assistant and v0 work together. Your assistant reads your code — the design tokens, the surface colors, the existing patterns — and gives v0 the context it needs. v0 comes back with expert design recommendations. Your assistant adapts them to your codebase conventions and applies the changes. One conversation, three capabilities working together.

<img src="https://raw.githubusercontent.com/Skie-Art/v0-ui-generator/main/assets/screenshots/claude-v0.gif" alt="AI assistant using v0 tools" width="480" />

---

<h2>✨ &nbsp; Two modes of working</h2>

### ❧ &nbsp; _Design consultation_

Tell your assistant what's wrong — "the hover states feel invisible" or "this button doesn't match the rest of the UI." It reads your code, sends v0 the design context, and v0 comes back with specific fixes: oklch values, className snippets, multiple options ranked from subtle to expressive, and the rationale behind each choice.

_"Why do my hover states disappear in dark mode?" "Is this button accessible on this surface?" "Give me three options for this card's focus state — subtle to bold."_

<img src="https://raw.githubusercontent.com/Skie-Art/v0-ui-generator/main/assets/screenshots/design-consultation.png" alt="Design consultation mode" width="670" />

### ✧ &nbsp; _Component generation_

Describe what you want in natural language. v0 generates production-ready React/TSX. Your assistant refines it with follow-up messages, extracts the files, and adapts them to your codebase patterns.

_Perfect for: scaffolding new components, building themed interfaces, generating design system lookbooks, prototyping layouts._

<img src="https://raw.githubusercontent.com/Skie-Art/v0-ui-generator/main/assets/screenshots/lookbook.gif" alt="Iterative refinement" width="480" />

---

<h2>↻ &nbsp; Iterative by design</h2>
v0 conversations persist across tool calls. Ask for a color palette, refine it with your constraints, generate a full interface, then iterate on the details — each message builds on the last. v0 learns your design language as the conversation progresses.

First pass not quite right? Send v0 your design system principles and it adjusts. Getting close but the shadows feel too heavy? Refine again. The conversation keeps its context so you're building on progress, not starting over.

**Real workflow example:**

1. `v0_generate_ui` — _"Establish a celestial astrology color palette with oklch tokens"_
2. `v0_refine_ui` — _"Now build a chat interface using that palette"_
3. `v0_refine_ui` — _"Add a design manifest lookbook page"_
4. `v0_get_files` — Extract the generated components

---

### ✻ &nbsp; _Use cases_

| Scenario                                            | What happens                                                                                                                                               |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _"Fix the hover states on these buttons"_           | Your assistant reads the code and surface colors, v0 returns three options with oklch values, contrast ratios, and rationale — ranked subtle to expressive |
| _"Build a dark celestial chat interface"_           | v0 generates a full themed component — custom color tokens, micro-interactions, SVG icons, responsive layout                                               |
| _"These don't match our design system"_             | Send v0 your design principles, it adjusts its recommendations to match your conventions                                                                   |
| _"Create a design system lookbook"_                 | v0 produces a visual reference page with color swatches, typography scale, and interactive component states                                                |
| _"The shadow feels too heavy, make it more raised"_ | Refines the previous generation with your feedback — no re-explaining context, it remembers the conversation                                               |

---

### ➾ &nbsp; _Getting started_

**1. Get an API key**

Go to [v0.app/chat/settings/keys](https://v0.app/chat/settings/keys) and create a key. Requires a [v0 Premium or Team plan](https://v0.app/pricing).

**2. Set your key**

**VS Code / GitHub Copilot:**

Run `v0: Set API Key` from the Command Palette (`Ctrl+Shift+P`). The status bar shows `✓ v0` when connected. The v0 tools are immediately available to Copilot and other VS Code MCP consumers.

**Claude Code:**

```bash
claude mcp add v0-ui-generator -e V0_API_KEY=your-key-here -- npx v0-ui-generator
```

Restart your Claude Code session and verify with `v0_setup_check`.

**3. Start building**

Ask your AI assistant to generate UI. It will call the v0 tools automatically.

---

<h2>⌘ &nbsp; 12 MCP tools</h2>

| Tool                   | What it does                                                     |
| ---------------------- | ---------------------------------------------------------------- |
| **Generation**         |                                                                  |
| `v0_generate_ui`       | Generate UI from a text prompt — returns source files + chat URL |
| `v0_refine_ui`         | Iterate on an existing generation with follow-up context         |
| **Extraction**         |                                                                  |
| `v0_get_chat`          | Retrieve full chat history and metadata                          |
| `v0_get_files`         | Extract generated source files from a chat                       |
| **Chat management**    |                                                                  |
| `v0_list_chats`        | List chats from the v0 API                                       |
| `v0_list_active_chats` | List chats tracked in the current session                        |
| `v0_set_active_chat`   | Switch which chat receives refinements                           |
| **Projects**           |                                                                  |
| `v0_create_project`    | Create a v0 project with shared design instructions              |
| `v0_list_projects`     | List all projects                                                |
| `v0_assign_to_project` | Assign a chat to a project                                       |
| **Operations**         |                                                                  |
| `v0_check_deployment`  | Get deployment logs and errors                                   |
| `v0_setup_check`       | Validate API connectivity and account info                       |

---

## Requirements

- [v0 Premium or Team plan](https://v0.app/pricing)
- Node.js 22+
- VS Code 1.97+

## Built with

- [v0-sdk](https://www.npmjs.com/package/v0-sdk) — Vercel v0 Platform API SDK
- [@modelcontextprotocol/sdk](https://github.com/modelcontextprotocol/typescript-sdk) — MCP server framework

## License

MIT

---
