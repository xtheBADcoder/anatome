# Contributing to Anatome Studio 🧬

Thank you for your interest in contributing to **Anatome Studio**! Our mission is to build an open, accessible, and high-performance biocomputational operating system that accelerates real-world therapeutic discoveries.

Whether you are a **computational chemist**, **structural biologist**, **machine learning researcher**, or **full-stack developer**, your contributions directly shape tools used to explore novel therapeutics.

---

## 🌟 The Vision: Tools for Scientific Breakthroughs

Drug discovery has historically been gated behind $30,000/seat desktop licenses, fragile CUDA environments, and siloed data formats. We believe the next generation of life-saving medicines will come from:
1. **Democratized Access:** Anyone with a browser and an idea should be able to fold a protein pocket, dock a ligand, and generate lead candidates in seconds.
2. **Atomic-Scale 3D Physics:** Moving beyond text tokens into $SE(3)$ spatial equivariance and continuous biophysical manifolds.
3. **Closing the Loop:** Connecting in-silico generation with laboratory automation and verifiable regulatory audit trails.

---

## 🔬 High-Impact Contribution Tracks

We actively encourage contributions across four primary domains:

### 1. Structural Biology & Biophysics Track
- **New Foundation Model Wrappers:** Integrate state-of-the-art models (AlphaFold 3, Boltz-1, Chai-1, ESM3, RFdiffusion) into our execution pipeline.
- **Biophysical Validation:** Benchmarking docking poses against PDBbind benchmarks, adding covalent docking, or integrating MM-GBSA / FEP+ scoring.
- **3D Visualization:** Extending our Mol* / VTK.js rendering with hydrogen bond surface meshes, electrostatic potential maps, and conformational trajectory playback.

### 2. Machine Learning & Model Studio Track
- **LoRA / PEFT Recipes:** Pre-configured fine-tuning pipelines for specific target classes (Kinases, GPCRs, Ion Channels, PROTACs).
- **Benchmarking & Datasets:** Curating standardized ChEMBL/BindingDB benchmarks for kinase selectivity and ADMET liabilities.
- **Agent Reasoning:** Enhancing the BioNeMo autonomous ReAct copilot with specialized scientific tool calling and error-recovery loops.

### 3. Lab Automation & Physical Wet-Lab Track
- **Robotics Drivers:** Adding connectors for Opentrons (OT-2/Flex API), Hamilton Venus, and Beckman Biomek liquid handlers.
- **Assay Protocol Compilers:** Mapping computational screening hits into automated cherry-picking 96/384-well plate worklists.

### 4. Full-Stack & Developer Experience Track
- **Performance:** WebGL/WebGPU acceleration for large protein complexes.
- **Self-Hosting:** Streamlined Docker-Compose and Helm charts for academic lab clusters.

---

## 🛠️ Getting Started with Local Development

### 1. Fork & Clone
```bash
# Fork the repository on GitHub, then clone your fork:
git clone https://github.com/YOUR_USERNAME/anatome.git
cd anatome

# Install frontend dependencies
npm install

# Start local Vite development server
npm run dev
```

### 2. Running the Python Backend (Optional)
```bash
cd backend
python -m venv venv

# Windows
venv\Scripts\activate
# Linux/macOS
# source venv/bin/activate

pip install -r requirements.txt
cp .env.example .env

uvicorn main:app --reload --port 8000
```

---

## 📜 Contributor License Agreement (CLA)

Because Anatome Studio uses a dual-licensing structure (AGPLv3 for open-source and commercial licensing for closed enterprise environments), **all contributors must sign our Contributor License Agreement**.

- When you submit a Pull Request, the automated **CLA Assistant** bot will comment on your PR.
- You can sign the agreement simply by replying to the bot with:  
  `I have read the CLA Document and I hereby sign the CLA`
- You can review the full legal agreement in [cla.md](cla.md).

---

## 🏆 Publishing & Scientific Breakthrough Recognition

If you use Anatome Studio in your research or co-develop a model that leads to a scientific discovery:
1. **Citation:** Please cite Anatome Studio in your preprints and papers:
   ```bibtex
   @software{anatome_studio_2026,
     author = {Anatome Studio Contributors},
     title = {Anatome Studio: An Open Biocomputational Operating System for Molecular Drug Discovery},
     url = {https://github.com/xtheBADcoder/anatome},
     year = {2026}
   }
   ```
2. **Hall of Breakthroughs:** We feature published discoveries, novel binders, and academic preprints powered by Anatome on our official platform and community showcase!

---

## 💬 Community & Questions

- **GitHub Discussions / Issues:** Use GitHub Issues for bug reports, model requests, and technical RFCs.
- **Email:** `contact@anatomestudios.com` for research partnerships, academic compute grants, or collaborative benchmarks.
