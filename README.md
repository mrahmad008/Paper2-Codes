# Simulation Codes for Physical-Layer Secret Key Generation in IRS-Assisted Ambient Backscattered Wireless Communication Networks
This repository contains the Python-based simulation code used to generate the results presented in our study on Physical-Layer Secret Key Generation in IRS-assisted ambient backscattered wireless communication networks. The repository supports the reproducibility of the results reported in the manuscript.

## Overview

The considered system model includes an ambient RF source, two backscatter tags (Tag 1 and Tag 2), and an intelligent reflecting surface (IRS).

Three configurations are evaluated for physical-layer secret key generation:

- **Without IRS:** Secret key generation without IRS assistance.
- **Single-Bit Feedback (SBF):** The IRS phase shifts are iteratively perturbed, and one feedback bit indicates whether the estimated triangle-channel gain has improved.
- **Perfect CSI:** The IRS phase shifts are optimized using perfect channel state information as an ideal benchmark.

The repository also includes simulations for mutual information (MI), bit disagreement rate (BDR), SBF convergence, and parameter sensitivity using cyclic prefix-based triangle-channel extraction.

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
| RF source–$T_1$ distance | 8 | m |
| RF source–$T_2$ distance | 7 | m |
| $T_1–T_2$ distance | 3 | m |
| $T_1$–IRS distance | 3 | m |
| IRS–$T_2$ distance | 3 | m |
| Downlink tap length ($l_{g_1}$) | 8 | samples |
| Downlink tap length ($l_{g_2}$) | 7 | samples |
| Direct $T_1$–$T_2$ tap length ($l_{g_{12}}$) | 3 | samples |
| SNR range | 0–30, step 5 | dB |
| Channel realizations per SNR point | 5000 | -- |
| Total number of SBF iterations ($K$) | 30 | -- |
| SBF perturbation bound ($\delta$) | $\pi/20$ | rad |
