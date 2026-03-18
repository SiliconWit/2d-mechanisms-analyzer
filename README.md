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

Product page for the SiliconWit 2D Mechanisms Analyzer, a suite of interactive browser-based simulators for planar mechanism design and analysis. Currently features the Crank-Slider Mechanism Simulator with kinematic analysis, force analysis, and professional report generation.

## File Structure

```
2d-mechanisms-analyzer/
├── index.mdx
├── crank-slider-mechanism-simulator.mdx
└── README.md
```

## How to Contribute

1. Fork the repository: [SiliconWit/2d-mechanisms-analyzer](https://github.com/SiliconWit/2d-mechanisms-analyzer)
2. Create a feature branch: `git checkout -b feature/your-topic`
3. Make your changes and commit with a clear message
4. Push to your fork and open a Pull Request against `main`
5. Describe what you changed and why in the PR description

## Content Standards

- All content files use `.mdx` format
- Focus on clear, accessible descriptions of simulator capabilities
- Include links to live simulators and related course experiments
- Use Starlight components where appropriate

## Local Development

Clone the main site repository and initialize submodules:

```bash
git clone --recurse-submodules <main-repo-url>
cd siliconwit-com
npm install
npm run dev
```

## License

This content is released under the [MIT License](LICENSE).
