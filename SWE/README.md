# Shallow Water Equations Experiment

All code for the shallow water experiments is contained in the `SWE` folder. It includes the data-generation script, the nonlinear learned model notebook, and the optimal linear baseline notebook.

Run the SWE workflow from the repository root so that `data/`, `test_data/`, and `inv_model_fc.pth` are written in the right place.

To get started, install the packages used here:

```bash
pip install torch torchvision numpy matplotlib
```

## Files

- `createSWEdata.py`
  - Generates the training tensors for the four main initial-condition families:
    - `Gaussian Bump`
    - `2 Gaussian Bumps`
    - `Sinusoidal Wave Pattern`
    - `Flat Conditions`
  - Creates the files
    - `data/train_x1_<ic_name>_allBatch_Close.pt`
    - `data/train_ic_<ic_name>_allBatch.pt`

- `final_SW.ipynb`
  - Main notebook for the nonlinear learned model.
  - If you are starting from scratch, first run the data-assembly block at the top of the notebook. It combines the per-condition training tensors into:
    - `data/training_data_10000.pt`
    - `data/ic_training_data_10000.pt`
  - The rest of the notebook defines the model, runs training, saves `inv_model_fc.pth`, and makes the nonlinear reconstruction and error plots.
  - The later sections of the notebook use the aggregated testing files in `test_data/`.

- `linear_SW.ipynb`
  - Computes the optimal linear inverse map using the aggregated training tensors.
  - Creates the in-distribution testing files:
    - `test_data/testing_data_2000.pt`
    - `test_data/ic_testing_data_2000.pt`
  - Creates the out-of-distribution testing files:
    - `test_data/OOD_testing_data_2000.pt`
    - `test_data/OOD_ic_testing_data_2000.pt`
  - Evaluates the linear baseline on both the in-distribution and OOD testing sets.

## Typical Order

If you are running the full SWE workflow from scratch, the usual order is:

1. Run `createSWEdata.py`
2. Open `final_SW.ipynb` and run the first data-assembly block to create `training_data_10000.pt` and `ic_training_data_10000.pt`
3. Continue through `final_SW.ipynb` to train the nonlinear model and save `inv_model_fc.pth`
4. Run `linear_SW.ipynb` to compute the optimal linear baseline and create the aggregated files in `test_data/`
5. Return to the later testing sections in `final_SW.ipynb` once the `test_data/*.pt` files have been created

The nonlinear notebook and the linear notebook are both written to be run top to bottom.

<div align="center">
  <img src="../README-Pics/ic.png" alt="Shallow water initial condition" width="450" />
</div>

<div align="center">
  <img src="../README-Pics/linPred.png" alt="Shallow water linear prediction" width="450" />
</div>
