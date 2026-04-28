## Data-Driven-DeepONet-for-2D-DLD-Microfluidic-Flow-Prediction



This repository contains a DeepONet-based surrogate model for predicting steady 2D Stokes velocity fields in parametric DLD-type microfluidic geometries.

## Contents

- Jupyter notebook for preprocessing, training, and evaluation
- README with setup instructions
- External dataset link

## Problem

The goal is to learn a mapping from a 7-parameter geometry vector

theta = [r_1, r_2, y_1, y_2, y_3, y_4, x_1]

to the corresponding velocity field \((u,v)\) in a four-pillar microfluidic channel.

## Model

The final model is a DeepONet with:
- branch input: normalized geometry vector
- trunk input: (x, y, sdf)
- latent dimension: 50
- hidden width: 100
- depth: 5 layers

The signed distance function (SDF) is included in the trunk input to encode pillar proximity.

## Dataset

- 1936 COMSOL simulations
- 1045 training cases
- 387 validation cases
- 504 test cases
- 5849 irregular mesh points per simulation

**Google Drive data link:** 

## Main result

The final model achieves:
- mean relative \(L_2\) error: 6.96e-2
- median: 6.53e-2

The main residual errors occur in low-velocity downstream regions, while near-pillar high-gradient structures are well reconstructed.

## Usage

1. Clone the repository
2. Download the dataset from Google Drive
3. PLEASE Update the data path in the notebook
4. Run the notebook cells for preprocessing, training, and evaluation

