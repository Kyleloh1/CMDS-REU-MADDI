# Nonlinear Biomedical Imaging with MedMNIST

This folder contains the nonlinear MedMNIST experiments based on a median-blur forward operator. The main notebooks cover the nonlinear forward problem, the nonlinear inverse problem, and a comparison notebook that reads the saved sweep results.

Run these notebooks from inside the `NonlinearMedMNIST` folder.

To get started, install the packages used here:

```bash
pip install torch torchvision medmnist numpy matplotlib
```

## Main Notebooks

- `forwardNonlinearMedMNIST.ipynb`
  - Builds blurred observations with the median filter.
  - Runs the nonlinear forward experiment.
  - Creates example figures under `E2EForward_Nonlinear/Example`.
  - Saves rank-sweep matrices and plots under `E2EForward_Nonlinear/RankSweep`.

- `inverseNonlinearMedMNIST.ipynb`
  - Uses blurred noisy observations for the nonlinear inverse experiment.
  - Creates example figures under `E2EInverse_Nonlinear/Example`.
  - Saves rank-sweep matrices and plots under `E2EInverse_Nonlinear/RankSweep`.

- `comparisonplot.ipynb`
  - Loads the saved sweep matrices from the forward and inverse notebooks.
  - Produces the combined comparison plot after those two notebooks have already been run.

The main nonlinear notebooks run the same four MedMNIST datasets:

- `tissuemnist`
- `chestmnist`
- `organamnist`
- `retinamnist`

with ranks

- `25, 50, 75, ..., 775`

## Typical Order

1. Run `forwardNonlinearMedMNIST.ipynb`
2. Run `inverseNonlinearMedMNIST.ipynb`
3. Run `comparisonplot.ipynb` if you want the combined comparison figure

The folder also contains additional utility and comparison notebooks, but the three notebooks above are the main entrypoints for the nonlinear imaging workflow.

<div align="center">
  <img src="E2EForward_Nonlinear/Example/e2eforward_nonlinear_chestmnist_mapping7181_errorcomparison.png" alt="Nonlinear forward example" width="450" />
</div>

<div align="center">
  <img src="E2EForward_Nonlinear/RankSweep/Pics/e2eforward_nonlinear_ranksweep_200ep.png" alt="Nonlinear forward rank sweep" width="450" />
</div>

<div align="center">
  <img src="E2EInverse_Nonlinear/Example/e2einverse_nonlinear_chestmnist_mapping7181_errorcomparison.png" alt="Nonlinear inverse example" width="450" />
</div>
