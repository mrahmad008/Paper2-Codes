# Simulation Codes for Physical-Layer Secret Key Generation in IRS-Assisted Ambient Backscattered Wireless Communication Networks
This repository contains the Python-based simulation code used to generate the results presented in our study on Physical-Layer Secret Key Generation in IRS-assisted ambient backscattered wireless communication networks. The repository supports the reproducibility of the results reported in the manuscript.

## Overview

The considered system includes an ambient RF source, two backscatter tags (Tag 1 and Tag 2), and an intelligent reflecting surface (IRS).

Three configurations are evaluated for physical-layer secret key generation:

- **Without IRS:** Secret key generation without IRS assistance.
- **Single-Bit Feedback (SBF):** The IRS phase shifts are iteratively perturbed, and one feedback bit indicates whether the estimated triangle-channel gain has improved.
- **Perfect CSI:** The IRS phase shifts are optimized using perfect channel state information as an ideal benchmark.

The repository also includes simulations for mutual information (MI), bit disagreement rate (BDR), SBF convergence, and parameter sensitivity using noncoherent triangle-channel extraction.
