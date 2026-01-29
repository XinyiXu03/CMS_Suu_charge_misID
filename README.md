# Charge mis-ID factors (Coffea)

Coffea-based workflow to compute electron charge mis-identification rates using a tag-and-probe method, and derive data/MC scale factors.

## Overview
- **Goal:** compute charge mis-ID factors (ε) for electrons and the corresponding scale factors between data and MC.
- **Method:**
  - Tag-and-probe method to select electrons
  - Build ε as a function of probe pT and probe η
  - Compute SF = ε_data / ε_MC
  - Perform a constant fit to SF and get the fitted value + uncertainty
  - Could split results by different selection criteria (regions / tag bin / charge etc.)
- **Inputs:** 2024 EGamma data; Drell–Yan MC samples

## Quick start
1. **Copy the code**
   - Copy `charge_misID_code/` into your CASA working directory.

2. **Open the notebook and configure**
   - Open `18_12_25_data_MC.ipynb`
   - Update:
     - `client = Client(...)` (your scheduler/cluster)
     - input fileset JSON paths for data and DY MC
   
3. **Run**
   - Run the notebook cells to process samples and produce plots.
   - After processing, you can adjust:
     - binning via `rebin_probe_pt_eta(...)`
     - split criteria via `build_eps_hists(...)`
