# Financial Experiment

The `Financial` folder contains code for two case studies: `Synthetic` and `Market`. The notebooks are written to be run from inside the `Financial` folder so that the CSV and figure outputs land in the expected place.

To get started, install the packages used in these notebooks:

```bash
pip install numpy pandas scipy scikit-learn matplotlib torch yfinance requests
```

The market notebooks also need network access for market prices and the Fama-French data download.

## Synthetic

This case study uses generated data from a GARCH model to test the autoencoder pipeline.

- `toyDataGARCH.ipynb`
  - Run this first.
  - Generates the synthetic CSV files used by the rest of the synthetic workflow:
    - `assetReturns_garch.csv`
    - `latentFactors_garch.csv`
    - `factorLoadings_garch.csv`

- `syntheticAEScript.ipynb`
  - Reads the synthetic CSVs from `toyDataGARCH.ipynb`.
  - Runs the classic, optimal, PCA, and nonlinear autoencoder experiments.
  - Computes OPA and prints the factor-analysis results in the notebook.

- `plotter.ipynb`
  - Can be run after the synthetic CSVs are available.
  - Creates:
    - `figure1_returns_comparison.png`
    - `figure2_latent_factors.png`
    - `figure_sector_distribution.png`

For the synthetic pipeline, the usual order is:

1. Run `toyDataGARCH.ipynb`
2. Run `syntheticAEScript.ipynb`
3. Run `plotter.ipynb` if you want the saved figures

<div align="center">
  <img src="../README-Pics/synthVSMarket.png" alt="Synthetic vs market returns" width="450" />
</div>

<div align="center">
  <img src="../README-Pics/latent.png" alt="Latent factors" width="450" />
</div>

## Market

This case study uses real stock data.

- `stockUniverseNames.ipynb`
  - Optional helper notebook.
  - Generates `stockUniverseNames.csv`, which lists the stock universe along with sector and company names.

- `marketAEScript.ipynb`
  - Main notebook for the real-market experiment.
  - Builds the stock universe.
  - Downloads and processes the Fama-French factors.
  - Runs the classic, optimal, PCA, and nonlinear autoencoder comparisons.
  - Applies varimax rotation and reports the analysis in the notebook.

- `plotter.ipynb`
  - Also includes the market-side visualizations.
  - Uses downloaded price data and the synthetic CSVs to make side-by-side plots.

For the market workflow, the usual order is:

1. Run `marketAEScript.ipynb`
2. Run `plotter.ipynb` if you want the saved figures
3. Run `stockUniverseNames.ipynb` if you want to refresh `stockUniverseNames.csv`

## Outputs

The main files created by this folder are:

- `assetReturns_garch.csv`
- `latentFactors_garch.csv`
- `factorLoadings_garch.csv`
- `stockUniverseNames.csv`
- `figure1_returns_comparison.png`
- `figure2_latent_factors.png`
- `figure_sector_distribution.png`
