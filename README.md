# Anatome Studio 🧬

> **AI-Native Biocomputational Operating System for Molecular Drug Discovery**  
> Powered by NVIDIA BioNeMo microservices, 3D structural biology, private LoRA model adaptation, and wet-lab automation.

[![Live Demo](https://img.shields.io/badge/Demo-Live%20Platform-blue)](https://anatome-studio-3810.web.app)
[![License: PolyForm Noncommercial](https://img.shields.io/badge/License-PolyForm%20Noncommercial-green.svg)](LICENSE.md)
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

## 📜 Licensing

This repository is source-available under the **PolyForm Noncommercial License 1.0.0**.

- **Academic, Research & Non-Commercial Use:** Free to inspect, clone, and run for students, academic researchers, and non-commercial evaluation.
- **Commercial Deployment & Pharma Use:** Commercial use within for-profit biotechs, pharmaceutical pipelines, or paid consulting requires an **Anatome Commercial License**.

See [COMMERCIAL_TERMS.md](COMMERCIAL_TERMS.md) for licensing tiers and partner revenue-share details, or reach out to **licensing@anatome.bio**.
