# Biomedical Imaging with MedMNIST

This folder contains the linear and affine-linear MedMNIST experiments from the paper. The notebooks cover autoencoding, forward modeling, inverse recovery, and denoising.

Run these notebooks from inside the `MedMNIST` folder.

To get started, install the packages used here:

```bash
pip install torch torchvision medmnist numpy matplotlib
```

All of the main notebooks use `download=True`, so the MedMNIST datasets are downloaded automatically the first time you run them.

## Main Notebooks

- `ClassicMedMNIST.ipynb`
  - Standard linear autoencoder experiment.
  - Creates example figures and a rank sweep.
  - Saves outputs under `Classic/MedMNIST/Pics` and `Classic/MedMNIST/Matrices`.

- `ClassicAffLinMedMNIST.ipynb`
  - Affine-linear autoencoder experiment.
  - Saves outputs under `AffineLinear/MedMNIST/Pics` and `AffineLinear/MedMNIST/Matrices`.

- `e2eForMedMNIST.ipynb`
  - Linear forward end-to-end experiment.
  - Creates example plots, saved matrices, and a rank sweep under `E2EForward/MedMNIST`.

- `e2eInvMedMNIST.ipynb`
  - Linear inverse end-to-end experiment.
  - Creates example plots, saved matrices, and a rank sweep under `E2EInverse/MedMNIST`.

- `e2eForAffLinMedMNIST.ipynb`
  - Affine-linear forward experiment.
  - Saves outputs under `E2EForAffLin/MedMNIST`.

- `e2eInvAffLinMedMNIST.ipynb`
  - Affine-linear inverse experiment.
  - Saves outputs under `E2EInvAffLin/MedMNIST`.

- `NoisyMedMNIST.ipynb`
  - Linear denoising experiment.
  - Saves outputs under `Noisy/MedMNIST`.

- `NoisyAffLinMedMNIST.ipynb`
  - Affine-linear denoising experiment.
  - Saves outputs under `NoisyAffLin/MedMNIST`.

Across the main notebooks, the rank sweeps run on:

- `tissuemnist`
- `chestmnist`
- `organamnist`
- `retinamnist`

with ranks

- `25, 50, 75, ..., 775`

## Comparison Plotting

After the main notebooks have been run, the notebooks in `SpecialErrorComparisonPlotting/` can be used to make combined comparison figures:

- `classicAndAffLinForPlot.ipynb`
- `e2eBothforPlot.ipynb`
- `e2eBothAffLinforPlot.ipynb`
- `NoisyBothForPlot.ipynb`

These are useful once the primary outputs already exist.

## Typical Order

You can run the notebooks independently by task, but a common order is:

1. `ClassicMedMNIST.ipynb`
2. `ClassicAffLinMedMNIST.ipynb`
3. `e2eForMedMNIST.ipynb`
4. `e2eInvMedMNIST.ipynb`
5. `e2eForAffLinMedMNIST.ipynb`
6. `e2eInvAffLinMedMNIST.ipynb`
7. `NoisyMedMNIST.ipynb`
8. `NoisyAffLinMedMNIST.ipynb`
9. the optional notebooks in `SpecialErrorComparisonPlotting/`

Each notebook is meant to be run top to bottom.

<div align="center">
  <img src="Classic/MedMNIST/Pics/classic_chestmnist_mapping7181_errorcomparison.png" alt="Linear MedMNIST example" width="450" />
</div>

<div align="center">
  <img src="Classic/MedMNIST/Pics/classic_ranksweep_200ep.png" alt="Linear MedMNIST rank sweep" width="450" />
</div>

<div align="center">
  <img src="Classic/MedMNIST/Pics/aeFullComparison.png" alt="Comparison figure" width="600" />
</div>
