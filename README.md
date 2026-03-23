# Optimal Linear Baseline Models for Scientific Machine Learning

This repository accompanies the public arXiv manuscript [*Optimal Linear Baseline Models for Scientific Machine Learning*](https://arxiv.org/abs/2508.05831). The project was developed during the Summer 2025 Model Meets Data REU in Emory University's Math Department.

Contributors: [Alexander DeLise](https://www.linkedin.com/in/alexanderdelise/), [Kyle Loh](https://www.linkedin.com/in/kyle-loh-a2a3272a9/), [Krish Patel](https://www.linkedin.com/in/krish-patel-1a8804224/), [Meredith Teague](https://www.linkedin.com/in/meredithcteague/)

Advisors: Andrea Arnold, Matthias Chung

More about our project and the REU site:
- [Poster](https://drive.google.com/file/d/17J9OuRvrml7EGSp-HRn8MIwqGx3h9dij/view?usp=sharing)
- REU program page: <https://www.math.emory.edu/site/cmds-reuret/summer2025/>

This project is supported by NSF DMS-2349534.

# Instructions

## Basic Demo

The `demo.py` script provides a small synthetic example for the theoretically optimal forward, inverse, autoencoding, and denoising maps from `methods.py`.

To run it:

```bash
python demo.py
```

To generate affine-linear mappings instead, set `affine = True` inside `demo.py`.

## Biomedical Imaging

The imaging experiments are split into two folders:

- [`MedMNIST/README.md`](MedMNIST/README.md) for the linear and affine-linear MedMNIST notebooks
- [`NonlinearMedMNIST/README.md`](NonlinearMedMNIST/README.md) for the nonlinear median-blur experiments

Both imaging folders contain notebook-level instructions, output locations, and example figures.

## Financial Experiment

All finance experiments are documented in [`Financial/README.md`](Financial/README.md).

That guide covers:

- the synthetic GARCH pipeline
- the real-market pipeline
- the optional stock-universe notebook
- the plotting notebook and the figures it creates

## Shallow Water Equations Experiment

All shallow water instructions are in [`SWE/README.md`](SWE/README.md).

That guide covers:

- the data-generation script
- the nonlinear learned model notebook
- the optimal linear baseline notebook
- the order to run them and the files each step creates