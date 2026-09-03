# MRL-based Antimicrobial Peptide Generation

This repository contains a Jupyter notebook for generating antimicrobial peptides (AMPs) using the MRL framework with custom physicochemical constraints.
## Overview
The pipeline consists of:
1. Training a CNN classifier on the AMPlify dataset (AUC = 0.92).
2. Fine-tuning a pre-trained LSTM language model on a custom dataset of active AMPs.
3. Reinforcement learning (PPO) with physicochemical constraints (cationic charge, hydrophobicity, hydrophobic moment).
## Prerequisites

### 1. MRL Framework
This notebook requires the MRL framework.
Clone the official MRL repository and place it in the same directory as the notebook:
git clone https://github.com/DarkMatterAI/mrl.git
Note: The mrl/ directory must be in the same parent folder as the notebook.

### 2. Datasets
Place the following files in the data/ directory:
anti_microbial_peptides.csv – AMPlify dataset (~8300 peptides).
AMP.csv – Custom dataset of active antimicrobial peptides.

### 3. Dependencies
pip install -r requirements.txt

### 4. Usage
Run the Jupyter notebook:
jupyter notebook notebooks/MRL_proteins_amp_Alexis.ipynb

### 5. Output
The notebook exports the top-scoring generated sequences (rewards > 12) to:
results/AMP_MRL>12.csv

### 6. Compatibility
Notes on Compatibility
Paperspace users: The notebook includes fallback paths for the Paperspace environment.
fastprogress: Version 1.0.3 is required. The installation cell includes this specific version.
Pandas: A temporary patch is applied for the deprecated .append() method.
