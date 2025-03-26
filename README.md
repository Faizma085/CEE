# For CEE Repository

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

## License
This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute this software as long as you respect the license terms.

---

**Thank you for using and contributing to this repository!**  
- If you find these notebooks helpful, please star the repo.  
- Feel free to open issues or pull requests with improvements or bug reports.
