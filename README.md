# Data Augmentation in Amyloid Protein Classification Using Generative Models

This repository contains the source code, data, and models developed for a Master's Thesis investigating the impact of artificial data augmentation on machine learning models classifying amyloid proteins. 

## Project Overview

The primary challenge addressed in this work is the limited availability and high redundancy of sequential data regarding amyloid proteins. The main objective was to evaluate how augmenting training datasets with artificially generated amino acid sequences affects the classification performance of traditional and deep machine learning architectures, alongside evaluating the biological viability of the generated peptides.

Three generative architectures performing conditional sequence generation guided by physicochemical features were developed and implemented:
1. **Conditional Variational Autoencoder (cVAE)** with a self-attention mechanism.
2. **ProtGPT2** (an autoregressive transformer language model).
3. **Conditional Diffusion Model**.

Synthetic sequences were filtered using a two-stage process: a statistical stage (via $z$-score thresholds) and a structural evaluation stage utilizing the **AlphaFold2** algorithm. The resulting datasets were then leveraged to train classical machine learning and deep learning classification networks.

---

## Repository Structure

The project workspace is structured as follows:

```text
anaconda_projects/
├── DataPrep.ipynb             # Initial data preprocessing, cleaning, and feature extraction
├── Datasets_filtering.ipynb   # Filtering pipelines
├── cVAE.ipynb                 # Implementation & training of the Conditional VAE with Self-Attention
├── ProtGPT2.ipynb             # Fine-tuning & conditional generation using the ProtGPT2 language model
├── Diffusion.ipynb            # Implementation and conditional sampling using the Diffusion model
├── Models_training.ipynb      # Training and evaluating ML/DL classifiers on augmented datasets + statistical tests
├── db/                        
└── files/                     # Working datasets, structural evaluations, and trained checkpoints
    ├── data/                  # Segmented intermediate data subsets
    ├── final_datasets/        # Clean reference and augmented final datasets used for classification
    ├── generated_datasets/    # Raw synthetic outputs from cVAE, ProtGPT2, and Diffusion models
    ├── models/                # Saved weights and serialized model artifacts (.pt, .pkl, etc.)
    ├── plots/                 # Analysis plots
    └── statistics_tests/      # Detailed outputs from statistical significance testing
