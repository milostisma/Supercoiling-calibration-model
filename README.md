# Supercoiling-calibration-model
This repository contains the analytical model used in Tisma et al. to predict the SYTOX Orange concentration needed for inducing precise supercoiling density in sufrace-bound single-molecule assay

## What the model does

The notebook:

- Computes SYTOX Orange binding to DNA using an excluded-site binding model.
- Estimates the number of bound dye molecules at a given dye concentration.
- Converts dye-induced DNA unwinding into a change in linking number.
- Accounts for torsional constraint and torque-dependent dye binding.
- Estimates final DNA supercoiling density after dye washout.
- Solves for the initial SYTOX Orange concentration needed to reach target supercoiling densities.
- Generates calibration plots for experimental planning.

## Main assumptions

The model assumes:

- DNA is torsionally constrained after surface attachment.
- SYTOX Orange binds DNA as an intercalator with excluded-site behavior.
- Each bound dye molecule unwinds the DNA by a fixed angular amount.
- Each bound dye molecule slightly increases the DNA contour length.
- After dye washout, the difference in bound dye molecules before and after washout produces an effective linking-number change.
- A fraction of the linking-number change is stored as twist, with the remainder stored as writhe.
- Dye binding can be affected by the torque state of the DNA.

## Key parameters

The notebook uses experimentally motivated parameters for DNA and SYTOX Orange binding, including:

| Parameter | Meaning |
|---|---|
| `Nbp` | DNA length in base pairs |
| `K` | SYTOX Orange binding association constant |
| `n` | Binding site size / excluded-site size |
| `delta_theta` | DNA unwinding angle per bound dye molecule |
| `delta_z` | DNA elongation per bound dye molecule |
| `C` | DNA torsional stiffness |
| `final_conc` | SYTOX Orange concentration after washout |
| `target_sigma` | Desired final DNA supercoiling density |