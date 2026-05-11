# CT→MRI Latent Diffusion Pipeline

A research-style end-to-end notebook project for **CT-to-MRI synthesis** using a **latent diffusion workflow** in PyTorch, with both generative and clinical evaluation stages.

## Project Structure

```text
.
├── ct_to_mri_latent_diffusion_pipeline.ipynb
└── README.md
```

## What This Notebook Covers

The notebook implements a multi-stage pipeline:

1. **Data setup and loading** for paired CT/MRI-style images.
2. **MRI autoencoder (VAE)** training and reconstruction analysis.
3. **CT→latent bridge model** training and evaluation.
4. **Conditional diffusion model (DDPM-style U-Net)** for MRI generation.
5. **Direct CT→MRI U-Net baseline** for comparison.
6. **Quantitative metrics logging** (e.g., PSNR/SSIM-related outputs to CSV).
7. **Clinical downstream stage** (tumor classification, ROC/confusion matrices, uncertainty/CI reporting).

## Environment

Core libraries used in the notebook include:

- `torch`, `torchvision`
- `numpy`, `pandas`
- `matplotlib`
- `scikit-image`
- `scikit-learn`
- `nibabel`
- `Pillow`
- `tqdm`

## Quick Start

1. Create and activate a Python environment (3.9+ recommended).
2. Install the required packages listed above.
3. Open the notebook:
   - `ct_to_mri_latent_diffusion_pipeline.ipynb`
4. Run cells in order.

## Expected Artifacts

During runs, the notebook can produce files such as:

- Checkpoints (`*.pth`)
- Visual outputs (`*.png`, `*.jpg`)
- Metrics reports (`generative_metrics.csv`, clinical evaluation CSVs)

## Suggested Repository Name

If you want a cleaner, publication-friendly repository name, a strong option is:

**`ct-to-mri-latent-diffusion-pipeline`**

## Notes

- This repository is notebook-centric by design.
- For reproducibility, keep datasets and large checkpoints outside the repository and link them in release assets or external storage.
