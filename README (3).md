# Ship Performance Data Analysis

**Python-based analysis of ship operational data**, focusing on wind-resistance corrections, speed–power performance, dry-docking effects, engine fuel consumption, and statistical outlier detection.

This project was developed as an academic assignment in Naval Architecture and Marine Engineering. The analysis is implemented in a Jupyter notebook using Python.

## Project overview

The notebook explores how measured operating conditions can be used to assess ship performance. In addition to exploratory data analysis, it applies engineering corrections and reference speed–power relationships to examine deviations in vessel performance.

The main tasks are:

1. **Exploratory data analysis:** Visualize shaft power, speed over ground (SOG), speed through water (STW), draft, trim, and propeller revolutions.
2. **Wind correction and performance analysis:** Estimate wind resistance and wind-corrected shaft power; compare operating data with reference speed–power curves and calculate speed loss and power deviation.
3. **Fuel consumption and power estimation:** Use engine shop-test fuel-consumption data to estimate brake power from main-engine fuel oil consumption.
4. **Outlier detection:** Examine propeller RPM measurements using statistical criteria, including Z-scores and Chauvenet's criterion.

## Methods and implementation

### 1. Exploratory data analysis

Time-series plots, scatter plots, and histograms are used to investigate operating conditions and identify trends in the measurements.

### 2. Wind resistance and ship performance

The notebook converts ship and wind measurements into a consistent set of variables and estimates wind resistance using a relation of the form

$$
R_{\mathrm{wind}} = \frac{1}{2}\rho_a V_{\mathrm{rel}}^2 A C_{\mathrm{wind}}.
$$

It then applies a wind-related shaft-power correction and compares the corrected observations with reference speed–power curves for different loading conditions. Performance indicators include **speed loss** and **power deviation**.

The analysis also compares these indicators **before and after a dry-docking period** using descriptive statistics and plots. These comparisons describe the available observations; they do not, on their own, establish that dry-docking caused any measured change.

### 3. Fuel consumption and power estimation

Engine shop-test points are used to construct a relationship between fuel oil consumption and brake power. A fitted curve is then applied to operational fuel-consumption measurements to estimate engine power and compare it with recorded power data.

### 4. Statistical outlier detection

The notebook applies window-based statistical analysis to propeller revolutions, using **Z-scores** and **Chauvenet's criterion** to flag potential outliers.

## Technologies

- **Python**
- **Jupyter Notebook / Google Colab**
- **pandas** and **NumPy** for data processing and numerical calculations
- **Matplotlib** and **Seaborn** for visualization
- **openpyxl** as the Excel reader used by pandas for `.xlsx` files

## Repository contents

```text
ship-performance-data-analysis/
├── README.md
└── ship_performance_analysis.ipynb
```

The repository contains the analysis notebook and documentation, **not the original operational dataset**.

## Dataset availability

> **The original dataset is not included in this repository due to its large file size.**

The analysis uses an Excel file named `ASKISI1_DATA_2026.xlsx`. The notebook refers to the original dataset in Google Drive. To reproduce the full analysis, the user must obtain that dataset separately and update the file path if needed.

Because the dataset is not provided here, the notebook is shared primarily to demonstrate the **analysis workflow, engineering calculations, and Python implementation**. The plots and numerical results cannot be fully reproduced from this repository alone.

## How to run

The notebook was written for **Google Colab** and mounts Google Drive to access the Excel dataset.

1. Open `ship_performance_analysis.ipynb` in Google Colab.
2. Make sure the required Python packages are available (`numpy`, `pandas`, `matplotlib`, `seaborn`, and `openpyxl`).
3. Place the original `ASKISI1_DATA_2026.xlsx` file in Google Drive.
4. Update this path in the first code cell if your file is stored elsewhere:

   ```python
   path = "/content/drive/MyDrive/ASKISI1_DATA_2026.xlsx"
   ```

5. Run the notebook cells in order.

The Google Drive mount (`from google.colab import drive`) is specific to Colab. To run the notebook locally in Jupyter, replace that step with a local Excel file path.

## Scope and limitations

- The analysis is based on one academic case study and the available operational measurements.
- Some engineering coefficients and reference curves are specified in the assignment and encoded in the notebook.
- Filtering rules, reference conditions, and the interpretation of performance deviations should be reviewed before applying the workflow to another vessel.
- This repository is a **code and methodology portfolio**, not a standalone dataset or independently reproducible benchmark.

## Project purpose

The work demonstrates practical use of Python for large-scale engineering data processing and visualization, alongside domain-specific ship-performance calculations and statistical assessment.
