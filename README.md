# Hackerster

### ULTRIX — Unified Layer for Tactical Reasoning and Intelligent eXecution

Hackerster is a multi-agent AI-assisted security assessment platform. This repository contains the interactive Founders Challenge presentation for the project.

## About

Hackerster is a multi-agent security assessment platform designed to coordinate specialized AI agents, real security tools, vulnerability knowledge and human approval into a single controlled workflow for authorized security assessments. Rather than a single AI model suggesting commands, Hackerster orchestrates a pipeline — discovery, enumeration, analysis, validation and reporting — where each stage is handled by a purpose-built agent, backed by real tool execution inside a sandboxed environment.

## Core Features

- Multi-agent architecture (Planner, Recon, Enumeration, Vulnerability, Validation, Reporting)
- Central orchestrator that coordinates the assessment workflow
- Per-agent model selection — each agent independently uses a local `.gguf` model or an API-based model
- Local-first AI support via local GGUF models and Ollama, alongside API-based cloud models
- Real security tool orchestration through a plugin-based architecture (Nmap, Nuclei, Gobuster, FFUF, Nikto, SQLMap, Hydra, WhatWeb, Subfinder, Amass, HTTPX, Naabu, Katana, Aircrack-ng, Metasploit, Impacket, and any registered tool)
- Sandboxed execution inside a Kali Linux Docker environment
- RAG (Retrieval-Augmented Generation) using a Qdrant vector database for grounded vulnerability analysis
- Knowledge graph (Neo4j) modeling relationships between targets, hosts, ports, services, technologies, vulnerabilities and findings
- Finding validation — every result is marked Confirmed, False Positive, or Uncertain before it reaches a report
- Human-in-the-loop risk gates — higher-risk actions require explicit researcher approval before execution
- Automated reporting in multiple formats (PDF, HTML, Markdown, JSON) across executive, technical, remediation, risk-dashboard, asset-inventory, attack-path and compliance report types

## Architecture

```
User
  ↓
Orchestrator (Planner)
  ↓
Specialized Agents (Recon → Enumeration → Vulnerability → Validation → Reporting)
  ↓
Controlled Environment (Kali Linux Docker sandbox + Safety/Risk Gate)
  ↓
Security Tools (Nmap, Nuclei, Gobuster, FFUF, Nikto, SQLMap, and more)
  ↓
Validation (Confirmed / False Positive / Uncertain)
  ↓
Reporting (PDF, HTML, Markdown, JSON)
```

## Presentation

This repository contains the interactive Founders Challenge presentation for Hackerster — a self-contained, single-file HTML presentation (`index.html`) covering the problem, the architecture, the six specialized agents, per-agent model selection, the RAG/knowledge graph context engine, tool orchestration, safety and human-in-the-loop controls, validation, reporting, the tech stack, and what differentiates the platform.

It includes a cinematic intro and outro, keyboard/arrow navigation, a progress bar and slide counter, fullscreen support, and interactive elements such as expandable agent cards, a clickable model-routing diagram, an animated knowledge-graph chain, and a toggleable approval-gate flow.

## Run Locally

No build steps or installation required.

1. Download or clone this repository.
2. Open `index.html` directly in any modern web browser (double-click it, or right-click → Open With → your browser).

**Note:** The presentation loads its typefaces (Inter and JetBrains Mono) from Google Fonts over the internet. If you open the file with no internet connection, everything still works exactly as designed — the presentation simply falls back to your system's default fonts instead of the custom ones. No other part of the presentation requires an internet connection or a local server.

## Deploy with GitHub Pages

1. Create a new repository on GitHub (or open an existing one).
2. Upload the contents of this project — `index.html` and `README.md` — to the repository.
3. Make sure `index.html` is in the **root** of the repository (not inside a subfolder).
4. Open the repository on GitHub and click **Settings**.
5. In the left sidebar, click **Pages**.
6. Under **Build and deployment → Source**, select **Deploy from a branch**.
7. Under **Branch**, select your main branch (e.g. `main`) and set the folder to **/ (root)**.
8. Click **Save**.
9. Wait a minute for GitHub to build the site, then open the generated URL shown at the top of the Pages settings (it looks like `https://<your-username>.github.io/<repository-name>/`).

The site will open directly into the Hackerster presentation.

## Team

### ULTRIX

Unified Layer for Tactical Reasoning and Intelligent eXecution

Members:
- Nidhish Gupta
- V.G. Harsh

Grade 9 — Section G

## Disclaimer

Hackerster is intended for authorized security assessments, educational purposes and controlled testing environments. Users must have permission to assess any target.
