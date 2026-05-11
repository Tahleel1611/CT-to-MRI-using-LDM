# CT → MRI using Latent Diffusion Models (LDM)

An end-to-end, notebook-based research pipeline for **CT-to-MRI image synthesis** using a **latent diffusion approach** in PyTorch, followed by both **image quality** and **clinical downstream** evaluation.

---

## ✨ Highlights

- 🧠 **Latent-space generation** rather than direct pixel-space generation
- 🔁 **Multi-stage training workflow** (VAE → CT-latent mapper → conditional diffusion)
- ⚖️ **Baseline comparison** with direct CT→MRI U-Net
- 📊 **Quantitative evaluation** (reconstruction/generation metrics + CSV logging)
- 🏥 **Clinical relevance check** via tumor classification and uncertainty-aware reporting

---

## 📁 Repository Structure

```text
.
├── ct_to_mri_latent_diffusion_pipeline.ipynb   # Full pipeline implementation
└── README.md                                   # Project overview and usage guide
```

> This repository is intentionally notebook-centric.

---

## 🧪 End-to-End Pipeline Overview

The notebook implements a staged workflow:

1. **Data Loading & Preparation**  
   Load paired CT/MRI-style samples and perform preprocessing for model training.

2. **MRI Autoencoder (VAE) Training**  
   Learn a compact latent representation of MRI data and assess reconstruction quality.

3. **CT → MRI-Latent Bridge Model**  
   Train a model that maps CT information into the learned MRI latent space.

4. **Conditional Diffusion (DDPM-style U-Net)**  
   Generate MRI outputs from CT-conditioned latent dynamics.

5. **Direct CT → MRI U-Net Baseline**  
   Train and compare a direct mapping baseline against the latent diffusion route.

6. **Generative Metric Logging**  
   Record metrics (e.g., PSNR/SSIM-related outputs) to CSV files for analysis.

7. **Clinical Downstream Evaluation**  
   Run tumor classification analyses, ROC/confusion assessments, and uncertainty/CI reporting.

---

## 🛠️ Tech Stack

Main libraries used in the notebook include:

- `torch`, `torchvision`
- `numpy`, `pandas`
- `matplotlib`
- `scikit-image`
- `scikit-learn`
- `nibabel`
- `Pillow`
- `tqdm`

---

## 🚀 Getting Started

### 1) Create an environment

Use Python **3.9+** (recommended):

```bash
python -m venv .venv
source .venv/bin/activate
```

Windows alternatives:

```powershell
# PowerShell
.venv\Scripts\Activate.ps1

# Command Prompt (cmd)
.venv\Scripts\activate.bat
```

### 2) Install dependencies

Install the libraries listed in the tech stack section (or your own pinned equivalents).

### 3) Open and run the notebook

Notebook to run:

- `ct_to_mri_latent_diffusion_pipeline.ipynb`

Run cells **top-to-bottom in order** to preserve stage dependencies.

---

## 📤 Typical Outputs

Depending on configuration and run length, you may generate:

- Model checkpoints (`*.pth`)
- Visual outputs (`*.png`, `*.jpg`)
- Metrics files (for example, `generative_metrics.csv` and clinical evaluation CSVs)
- Diagnostic plots (e.g., ROC curves/confusion matrix visualizations)

---

## 📌 Notes on Reproducibility

- Keep large datasets and heavyweight checkpoints outside the Git repository.
- Prefer external storage / release assets for artifact sharing.
- For consistent comparisons, keep preprocessing and split logic fixed across experiments.

---

## ⚠️ Current Scope

- This project is currently delivered as a **single comprehensive notebook**.
- There is no packaged module/API yet.
- Environment and dependency pinning may vary by runtime setup.
