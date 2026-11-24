# Anatome Studio 🧬

> **AI-Native Biocomputational Operating System for Molecular Drug Discovery**  
> Powered by NVIDIA BioNeMo microservices, 3D structural biology, private LoRA model adaptation, and wet-lab automation.

[![Live Demo](https://img.shields.io/badge/Demo-Live%20Platform-blue)](https://anatome-studio-3810.web.app)
[![License: AGPL v3](https://img.shields.io/badge/License-AGPL_v3-blue.svg)](LICENSE.md)
[![CLA Assistant](https://img.shields.io/badge/CLA-Required-brightgreen.svg)](cla.md)
[![NVIDIA BioNeMo](https://img.shields.io/badge/Powered%20By-NVIDIA%20BioNeMo-76B900.svg)](https://build.nvidia.com)

---

## 🌟 Overview

Anatome Studio is a next-generation platform integrating generative chemistry, protein folding, molecular docking, and wet-lab orchestration into a single reactive workspace. 

Unlike general LLM interfaces that operate purely on 1D text tokens, Anatome operates in **3D Euclidean atomic coordinates** ($SE(3)$ spatial equivariance), allowing computational chemists and biologists to fold target proteins, dock ligands, fine-tune proprietary foundation models, and dispatch assay plates.

---

## 🚀 Key Modules & Capabilities

- **🧬 ESMFold 3D Protein Folding:** Sub-2-second target structure prediction with per-residue pLDDT confidence coloring and interactive Mol* 3D rendering.
- **🎯 DiffDock V2 Molecular Docking:** Diffusion-based pose prediction and binding affinity scoring ($\Delta G$) for small-molecule candidate screens.
- **🧪 MolMIM Generative Chemistry:** High-affinity small-molecule generation in a continuous, biophysically constrained latent manifold (ensuring chemically valid, drug-like structures).
- **🔬 Model Studio (LoRA / PEFT Engine):** Private, customer-isolated fine-tuning on internal assay datasets (e.g. Kinase SAR, solubility, toxicity). Adapters remain customer-owned.
- **🤖 BioNeMo Autonomous Agent Toolkit:** Autonomous ReAct reasoning copilot powered by NVIDIA Nemotron that orchestrates multi-step discovery campaigns from target sequence to docked leads.
- **📋 FDA 21 CFR Part 11 Compliance:** Cryptographic SHA-256 electronic signatures, timestamped change-control logs, and immutable audit trails ready for regulatory filing.
- **🤖 Lab Automation & Robotics:** Direct OPC-UA & Tecan liquid-handling robotics dispatcher mapping computational hits into 96/384-well plate layouts.

---

## 📂 Repository Structure

```text
anatome/
├── .github/
│   └── workflows/
│       └── cla.yml             # Automated Contributor License Agreement (CLA) Assistant bot
├── backend/                    # Python / FastAPI biocomputational backend services
│   ├── Dockerfile              # Containerization for Cloud Run / AWS / local deployment
│   ├── main.py                 # FastAPI endpoints for BioNeMo NIM proxies, PDB prep, and simulations
│   ├── requirements.txt        # Backend dependencies (FastAPI, httpx, uvicorn, pydantic)
│   └── .env.example            # Backend environment template (NVIDIA NGC API keys)
├── public/                     # Static assets, SVG icons, and browser favicons
├── src/                        # React + TypeScript frontend application
│   ├── assets/                 # Brand graphics and 3D illustration assets
│   ├── App.tsx                 # Core workspace UI, 3D viewport, and tab orchestrator
│   ├── App.css                 # Platform component styling and layout definitions
│   ├── index.css               # Design tokens, theme variables, and global typography
│   └── main.tsx                # React application entry point
├── .env.example                # Frontend environment template
├── .gitignore                  # Git ignore rules (strictly guards keys, venv, and build artifacts)
├── cla.md                      # Legal Contributor License Agreement for external PRs
├── COMMERCIAL_TERMS.md         # Commercial dual-licensing terms and partner network details
├── LICENSE.md                  # GNU Affero General Public License v3 (AGPLv3)
├── package.json                # Frontend dependencies, scripts, and build metadata
└── README.md                   # Project documentation and quick-start guide
```

---

## 🛠️ Quick Start

### 1. Prerequisites
- **Node.js** v18+ and `npm`
- *(Optional)* Python 3.10+ (if running the local FastAPI backend)
- *(Optional)* NVIDIA NGC API Key (from [build.nvidia.com](https://build.nvidia.com)) for live NIM microservices. The app includes deterministic high-fidelity simulation fallbacks for offline testing.

### 2. Frontend Setup
```bash
# Clone the repository
git clone https://github.com/your-username/anatome.git
cd anatome

# Install dependencies
npm install

# Start Vite local development server
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

### 3. (Optional) Local Backend Setup
```bash
cd backend

# Create virtual environment
python -m venv venv
# On Windows:
venv\Scripts\activate
# On Linux/macOS:
# source venv/bin/activate

# Install requirements
pip install -r requirements.txt

# Copy example environment configuration
cp .env.example .env
# Fill in your NVIDIA_API_KEY in backend/.env

# Run server
uvicorn main:app --reload --port 8000
```

---

## ⚙️ Configuration & Live API Keys

Anatome supports **Hybrid Execution Mode**:
1. **Simulation Mode (Default):** Runs deterministic, realistic scientific simulations offline without needing an active NVIDIA API key or backend.
2. **Live NVIDIA NIM Mode:** Open **Settings** in the top navigation bar and enter your NVIDIA NGC API key (`nvapi-...`). The platform will directly invoke live hosted NIM microservices (ESMFold, DiffDock, MolMIM, Nemotron).

---

## 📜 Licensing & Dual-License Model

This repository is licensed under the **GNU Affero General Public License v3 (AGPLv3)**.

- **Open Source & Academic Research:** Free to inspect, clone, modify, and run under the terms of AGPLv3. Any network-accessible distribution or modification must be released under AGPLv3 copyleft terms.
- **Commercial & Enterprise Use:** If you wish to use Anatome Studio within a commercial pharmaceutical pipeline, CRO, or proprietary environment without being subject to the AGPLv3 copyleft open-source obligations, an **Anatome Commercial License** is required.

See [COMMERCIAL_TERMS.md](COMMERCIAL_TERMS.md) for commercial licensing tiers, private VPC deployment rights, and partner revenue-share details, or contact **licensing@anatome.bio**.

---

## 🤝 Contributing & Scientific Collaboration

We are building Anatome Studio as a collaborative engine for **real-world therapeutic breakthroughs**. Whether you are a computational chemist benchmark-testing new kinase binders, an ML researcher integrating novel diffusion architectures, or an open-source engineer, we welcome your contributions!

- 📖 **Contributor Guide:** See our [CONTRIBUTING.md](CONTRIBUTING.md) for active research tracks, local setup, and architectural guidelines.
- 🎯 **Good First Issues:** Check open issues tagged with `scientific-breakthrough` and `enhancement`.
- ✍️ **CLA Agreement:** When you submit a Pull Request, our automated **CLA Assistant** bot will prompt you to sign the [Contributor License Agreement](cla.md) via a single comment.

### 📚 Citation
If you use Anatome Studio in academic literature, preclinical discovery campaigns, or molecular engineering benchmarks, please cite:
```bibtex
@software{anatome_studio_2026,
  author = {Anatome Studio Contributors},
  title = {Anatome Studio: An Open Biocomputational Operating System for Molecular Drug Discovery},
  url = {https://github.com/xtheBADcoder/anatome},
  year = {2026}
}
```
