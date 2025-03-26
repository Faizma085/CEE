# For CEE Repository

This repository provides Jupyter notebooks for calculating (CDI, mRAI, mWBAI, MI) & (CWR, IWR) from NetCDF data.

## Table of Contents
1. [Overview](#overview)  
2. [Features](#features)  
3. [Repository Structure](#repository-structure)  
4. [Hardware & Performance](#hardware--performance)  
5. [References](#references)  
6. [License](#license)

---

## Overview
This repository enables you to:

- **Compute** water balance (precipitation minus evapotranspiration).  
- **Calculate** indices:  
  - **mRAI** (Modified Rainfall Anomaly Index)  
  - **mWBAI** (Modified Water Balance Anomaly Index)  
  - **MI** (Moisture Index), using Faiz et al. and Zhou & Qian methods  
  - **CDI** (Composite Drought Index) via PCA or weighted approaches  
- **Estimate** Crop Water Requirements (**CWR**) for multiple crops (maize, rice, wheat) using FAO-based Kc values.  
- **Compute** Effective Rainfall and derive Irrigation Water Requirement (**IWR**).  
- **Analyze** relationships (Random Forest models) between drought indices (e.g., CDI) and CWR/IWR.

---

## Features
- **Flexible Input**: Handles monthly NetCDF datasets for precipitation, evapotranspiration, etc.  
- **Multiple Indices**: Generates water balance, RAI, WBAI, MI, and composite drought indices.  
- **Crop Calculations**: Derives CWR, effective rainfall, and IWR for various crops and regions.  
- **Data Integration**: Interpolates, resamples, and slices time/space dimensions to align datasets.  
- **Advanced Analysis**: Random Forest regressions and SHAP interpretability to explore relationships among indices, CWR, and IWR.

---

## Repository Structure

```
├── README.md                 # This file
├── environment.yml or requirements.txt
├── data/                     # Example NetCDF input files
└── scripts/                  # Jupyter notebooks
    ├── WB_MRAI_CEE.ipynb
    ├── Global_MI_CDI_CEE.ipynb
    ├── CWR_CEE.ipynb
    ├── ER_IWR_CEE.ipynb
    └── RF_CEE.ipynb
```

### Key Dependencies
- **xarray** and **netCDF4**: for NetCDF data handling  
- **numpy**, **pandas**, **scipy**: for numerical operations and data manipulation  
- **scikit-learn**: for PCA, Random Forest, etc.  
- **shap**: for SHAP interpretability  
- **matplotlib**: for plotting  

---

## Hardware & Performance

These analyses can be computationally intensive, especially for large spatiotemporal NetCDF datasets. Below are some hardware considerations:

- **Tested Setup**:  
  - GPU: **NVIDIA RTX 3060** (Lenovo system)  
  - RAM: **128 GB**  
- **Recommendations**:  
  - **RAM**: At least 32 GB recommended for large multi-year, global NetCDF datasets.  
  - **GPU**: A dedicated GPU (such as an RTX series) accelerates certain operations, especially Random Forest or other machine learning tasks, though CPU-based runs are possible.  
  - **Storage**: Sufficient disk space for storing multiple NetCDF files (which can be large).  
  - **CPU**: Multi-core processor (e.g., 8+ cores) can speed up data pre-processing.

For smaller-scale or regional datasets, a lower-spec machine might suffice. For global analyses over long time periods, high memory and GPU acceleration can significantly improve performance.

---

## References

1. **Faiz, M. A. et al.** (2022). *A composite drought index developed for detecting large-scale drought characteristics*. *Journal of Hydrology*, 605, 127308.  
2. **Zhou, W., Liu, G., Pan, J., Feng, X.** (2005). *Distribution of available soil water capacity in China*. *Journal of Geographical Sciences*, 15(1), 3–12.  
3. **Qian, W., Shan, X., Zhu, Y.** (2011). *Ranking regional drought events in China for 1960–2009*. *Advances in Atmospheric Sciences*, 28, 310–321.  
4. **FAO** references for crop coefficients (Kc) and planting months (various sources).

---

## License
This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute this software as long as you respect the license terms.

---

**Thank you for using and contributing to this repository!**  
- If you find these notebooks helpful, please star the repo.  
- Feel free to open issues or pull requests with improvements or bug reports.
