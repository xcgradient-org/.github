# XC Gradient Monorepo

This repository is the central "Company OS" for XC Gradient. It manages documentation, internal tools, and serves as the orchestration point for our distributed services.

## 🏛️ Organization Structure

We have moved to a specialized repository structure under the [xcgradient-org](https://github.com/xcgradient-org) GitHub organization:

- **[brand-assets](https://github.com/xcgradient-org/brand-assets):** Centralized logos and brand identity (linked as a Git Submodule).
- **[latex-builder](https://github.com/xcgradient-org/latex-builder):** LaTeX build system and corporate document templates.
- **[pwp-builder](https://github.com/xcgradient-org/pwp-builder):** PowerPoint presentation automation.
- **[xcg-bot](https://github.com/xcgradient-org/xcg-bot):** Discord operational bot (Notion + Gemini AI).
- **[hw-management](https://github.com/xcgradient-org/hw-management):** Hardware health monitoring and reporting.
- **[local-ai](https://github.com/xcgradient-org/local-ai):** Local LLM (DeepSeek/Qwen) orchestration system.

## 🐳 Containerization & CI/CD

All core tools are now containerized and integrated with GitHub Actions:
- **Registry:** Production images are hosted at `ghcr.io/xcgradient-org/<repo-name>:latest`.
- **CI/CD:** Automatic linting, testing, and Docker builds on every push to `main`.
- **Deployment:** Services can be deployed anywhere using `docker pull`.

## 📂 Layout

```text
XCGradient/
├── docs/                 # Durable company & operating-system documentation
├── automation/
│   ├── xcg-bot/          # Discord Bot (Containerized)
│   └── hw-management/    # Hardware Monitor (Containerized)
├── latex-builder/        # LaTeX Builder (Submodule: brand-assets)
├── pwp-builder/          # PPTX Builder (Submodule: brand-assets)
├── local-ai/             # Local LLM System
├── brand-assets/         # Central Branding (Git Submodule)
└── Makefile              # Root orchestration
```

## 🚀 Getting Started with Submodules

When cloning this monorepo, ensure you initialize the submodules:

```bash
git clone --recursive git@github.com:Sterrysx/XCGradient.git
# Or if already cloned:
git submodule update --init --recursive
```

## Common Commands

Run these from the repository root:

```bash
make okr
make projects
make tasks
make verify
make bot
```

## LaTeX Build and Preview

This repository includes a shared LaTeX build workflow that compiles all root documents under:

- `latex-builder/projects/**/<project-name>.tex`
- `latex_DOCS/proposta/*.tex`

### Prerequisites

- TeX Live (or another LaTeX distribution) with `latexmk` and `biber` available on `PATH`

### Build Everything

From the repository root:

```bash
make latex-build-all
```

Or directly with scripts:

- Windows (PowerShell):

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File latex-builder/scripts/build-all.ps1
```

- Linux/macOS:

```bash
bash latex-builder/scripts/build-all.sh
```

### Clean Build Artifacts

```bash
make latex-clean-all
```

### VS Code Task

Use the default build task:

- `Terminal > Run Build Task...`
- Select `LaTeX: Build All PDFs`

This is configured in `.vscode/tasks.json` and works for both Windows and Unix-like systems.
