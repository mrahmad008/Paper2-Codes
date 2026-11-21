# Simulation Codes for Physical-Layer Secret Key Generation in IRS-Assisted Ambient Backscattered Wireless Communication Networks
This repository contains the Python-based simulation code used to generate the results presented in our study on Physical-Layer Secret Key Generation in IRS-assisted ambient backscattered wireless communication networks. The repository supports the reproducibility of the results reported in the manuscript.

## Overview

The considered system model includes an ambient RF source, two backscatter tags ($T_1$ and $T_2$), an intelligent reflecting surface (IRS), and an eavesdropper (Darth).

Three configurations are evaluated for physical-layer secret key generation:

- **Without IRS:** Secret key generation without IRS assistance.
- **Single-Bit Feedback (SBF):** The IRS phase shifts are iteratively perturbed, and one feedback bit indicates whether the estimated triangle-channel gain has improved.
- **Perfect CSI:** The IRS phase shifts are optimized using perfect channel state information as an ideal benchmark.

The repository also includes simulations for mutual information (MI), bit disagreement rate (BDR), secret key rate (SKR) under eavesdropper models, and parameter sensitivity using cyclic prefix-based triangle-channel extraction.

## Simulation Setup

A Python-based simulation framework was developed to evaluate the proposed IRS phase-adjustment algorithms under the considered Indoor channel conditions. The following table summarizes the simulation parameters used in the numerical evaluations:
| Parameter | Value | Unit |
|---|---|---|
| Number of OFDM subcarriers ($N$) | 256 | -- |
| Cyclic-prefix length ($N_{cp}$) | 64 | samples |
| Maximum backscattered channel spread ($l_{c_1}, l_{c_2}$) | 10 | samples |
| Usable CP samples ($J$) | 55 | samples |
| Number of IRS elements ($M$) | 128 | -- |
| BT reflection coefficient ($\beta$) | $0.3+0.4j$ ($\|\beta\|=0.5$) | -- |
| Power delay profile decay | 3 | dB/tap |
| Normalized transmit power ($P$) | 1 | -- |
| Path-loss exponent ($\eta$) | 3 | -- |
| RF source--$T_1$ distance | 8 | m |
| RF source--$T_2$ distance | 7 | m |
| $T_1$--$T_2$ distance | 3 | m |
| $T_1$--IRS distance | 3 | m |
| IRS--$T_2$ distance | 3 | m |
| Downlink tap length ($l_{g_1}$) | 8 | samples |
| Downlink tap length ($l_{g_2}$) | 7 | samples |
| Direct $T_1$–$T_2$ tap length ($l_{g_{12}}$) | 3 | samples |
| SNR range | 0–30, step 5 | dB |
| Channel realizations per SNR point | 5000 | -- |
| Total number of SBF iterations ($K$) | 30 | -- |
| SBF perturbation bound ($\delta$) | $\pi/20$ | rad |

## Reproducibility: Figure and Table Mapping

The following table maps each manuscript figure and simulation-generated table to its corresponding Python script and random seed.

| Manuscript Item | Description | Python Script | Random Seed |
|---|---|---|---|
| Figure 2 | Scatter plot of normalized triangle-channel estimates | [`figure2_code`](figure2_code) | 42 |
| Figure 3 | Mutual information between $u_1$ and $u_2$ vs. SNR | [`figure3_4_code`](figure3_4_code) | 42 |
| Figure 4 | Bit disagreement ratio after 1-bit median quantization vs. SNR. | [`figure3_4_code`](figure3_4_code) | 42 |
| Figure 5 | Mutual information between $u_1$ and $u_2$ vs. SNR for four scenarios | [`figure5_code`](figure5_code) | 42, confidence interval seed: 123 |
| Figure 6 | Secret key rate vs. SNR for eavesdropping model 1 | [`figure6_7_code`](figure6_7_code) | 42 |
| Figure 7 | Secret key rate vs. SNR for eavesdropping model 2 | [`figure6_7_code`](figure6_7_code) | 42 |
| Table 2 | Sensitivity analysis of the proposed PHYL key generation algorithm at an SNR of 20 dB | [`Table2_code`](Table2_code) | 42 |


### Reproducibility Notes

- All random seeds are fixed to support reproducible numerical experiments.
- Figure 5 and Table 2 use an independent random seed for their paired-bootstrap confidence-interval analysis.
- The scripts should be executed using the simulation parameters specified in the manuscript and the corresponding Python files.

We added comments to the Python files to explain the purpose of each simulation, the main parameters, and the corresponding results in the manuscript.

## Dependencies & Environment

All simulation scripts in this repository are written in Python and rely on standard scientific computing libraries.

### Core Dependencies

| Package / Tool | Verified Version | Purpose in Repository |
| :--- | :---: | :--- |
| **Python** | `3.13` | Execution runtime for simulation scripts |
| **NumPy** | `2.1.3` | OFDM signal generation, channel modeling, IRS phase optimization, and Monte Carlo simulations |
| **SciPy** | `1.16.3` | Numerical computations, interpolation, statistical analysis, and kNN-based information estimation |
| **Matplotlib** | `3.10.0` | Generating MI, BDR, SBF convergence, and sensitivity analysis figures |
| **pandas** | `2.2.3` | Organizing simulation results and exporting CSV files |
| **scikit-learn** | `1.6.1` | Mutual information estimation using `mutual_info_regression` |

### Quick Installation

Install all required packages in a single step via `pip`:

```bash
pip install "numpy>=2.1.3" "scipy>=1.16.3" "matplotlib>=3.10.0" "pandas>=2.2.3"
```

