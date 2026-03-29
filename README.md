---
title: "2D Mechanisms Analyzer - Collaboration Guide"
description: "Contributing guide for 2D Mechanisms Analyzer product content"
tableOfContents: true
sidebar:
  order: 999
---

# 2D Mechanisms Analyzer

![Build](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Contributors Welcome](https://img.shields.io/badge/contributors-welcome-orange)

**Read this page at:** [https://siliconwit.com/product-development/2d-mechanisms-analyzer/](https://siliconwit.com/product-development/2d-mechanisms-analyzer/)

Product page for the SiliconWit 2D Mechanisms Analyzer, a suite of interactive browser-based simulators for planar mechanism design and analysis. Features the Crank-Slider Mechanism Simulator, Four-Bar Linkage Simulator, and Scissor Lift Mechanism Simulator with kinematic analysis, force analysis, stability analysis, and professional report generation.

## File Structure

```
2d-mechanisms-analyzer/
├── index.mdx
├── crank-slider-mechanism-simulator.mdx
├── four-bar-linkage-simulator.mdx
├── scissor-lift-mechanism-simulator.mdx
└── README.md
```

## How to Contribute

All commands below work on Linux, macOS, and Windows (using Git Bash, PowerShell, or Command Prompt with Git installed).

### For Team Members (with push access)

**First time setup (clone the repo once):**

```bash
git clone https://github.com/SiliconWit/2d-mechanisms-analyzer.git
cd 2d-mechanisms-analyzer
```

**Every time you start working:**

```bash
git pull origin main
```

Always pull before making changes. This avoids conflicts with other contributors.

**After making your changes:**

```bash
git add .
git commit -m "Brief description of what you changed"
git push origin main
```

**If you get a push error** (someone pushed before you):

```bash
git pull origin main
```

Git will merge the changes automatically in most cases. If there is a conflict, Git will mark the conflicting lines in the file. Open the file, choose which version to keep, then:

```bash
git add .
git commit -m "Resolve merge conflict"
git push origin main
```

**Tips to avoid conflicts:**

- Always `git pull origin main` before you start working
- Push your changes as soon as you are done, do not hold onto uncommitted work for long
- Coordinate with other contributors so two people are not editing the same file at the same time

### For External Contributors (without push access)

1. Fork the repository: [SiliconWit/2d-mechanisms-analyzer](https://github.com/SiliconWit/2d-mechanisms-analyzer)
2. Clone your fork:
   ```bash
   git clone https://github.com/YOUR-USERNAME/2d-mechanisms-analyzer.git
   cd 2d-mechanisms-analyzer
   ```
3. Make your changes and commit:
   ```bash
   git add .
   git commit -m "Brief description of what you changed"
   git push origin main
   ```
4. Open a Pull Request against `main` on the original repository
5. Describe what you changed and why in the PR description

## Content Standards

- All content files use `.mdx` format
- Focus on clear, accessible descriptions of simulator capabilities
- Include links to live simulators and related course experiments
- Use Starlight components (`<Tabs>`, `<TabItem>`, `<Steps>`, `<Card>`) where appropriate
- Each simulator page should include: feature overview, preset table, equations, guided experiments links, and related resources

## Local Development

To preview the full site locally, clone the main site repository and initialize submodules:

```bash
git clone --recurse-submodules <main-repo-url>
cd siliconwit-com
npm install
npm run dev
```

To test a production build:

```bash
npm run build
```

## License

This content is released under the [MIT License](LICENSE).
