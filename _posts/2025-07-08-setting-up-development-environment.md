---
title: "Setting Up a Development Environment"
date: 2025-07-08 11:00:00 -0500
categories: [Development, Setup]
tags: [environment, tools, productivity, vscode]
image:
  path: /assets/img/posts/dev_environment.png
  alt: Development Environment Setup
---

# Creating an Efficient Development Environment

Setting up a productive development environment is crucial for any programmer. In this post, I'll share my current setup and the tools that help me stay productive.

## Code Editor: Visual Studio Code

I've settled on VS Code as my primary editor due to its excellent extension ecosystem and built-in features.

### Essential Extensions

Here are the extensions I consider must-haves:

```json
{
  "recommendations": [
    "ms-python.python",
    "bradlc.vscode-tailwindcss",
    "esbenp.prettier-vscode",
    "ms-vscode.vscode-typescript-next"
  ]
}
```

### Custom Settings

My `settings.json` includes these productivity boosters:

```json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.organizeImports": true
  },
  "workbench.colorTheme": "One Dark Pro",
  "editor.fontFamily": "Fira Code",
  "editor.fontLigatures": true
}
```

## Terminal Setup

I use **Windows Terminal** with **PowerShell 7** for better compatibility and features.

### Useful Aliases

```powershell
# Git shortcuts
function gs { git status }
function ga { git add $args }
function gc { git commit -m $args }
function gp { git push }

# Directory navigation
function ll { Get-ChildItem -Force }
function .. { Set-Location .. }
```

## Version Control

Git configuration that saves time:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Package Managers

- **Node.js**: Using npm/yarn for JavaScript projects
- **Python**: pip with virtual environments

## Key Takeaways

1. **Consistency**: Use the same tools across projects
2. **Automation**: Set up formatters and linters to run automatically
3. **Customization**: Tailor your environment to your workflow
4. **Documentation**: Keep notes on your setup (like this post!)

A well-configured development environment can significantly boost productivity and reduce friction when switching between projects.

---

*What tools are essential in your development setup? Share your must-have extensions and configurations in the comments!*
