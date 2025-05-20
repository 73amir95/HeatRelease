# Heat Release and PCS Analysis

## Overview
This Python script analyzes heat release and PCS (potentially compressive strength) data from two Excel files: `HeatRelease.xlsx` and `20C_PCC_HeatRelease_All_28d_Alex.xlsx`. It performs data loading, cleaning, statistical analysis, and visualization to explore heat release and PCS over time for different material samples (EVA, SA, SBR, and REF) at varying conditions.

## Dependencies
To run the script, ensure the following Python libraries are installed:
- `numpy`: For numerical computations
- `pandas`: For data manipulation and analysis
- `matplotlib`: For creating plots
- `seaborn`: For enhanced statistical visualizations

Install the dependencies using pip:
```bash
pip install numpy pandas matplotlib seaborn
```

## Data
The script processes data from two Excel files:

### 1. `HeatRelease.xlsx`
- **Sheet: HeatRelease**
  - Columns: `time`, `heattotal_EVA_05`, `heattotal_EVA_15`, `heattotal_SA_05`, `heattotal_SA_15`, `heattotal_SBR_05`, `heattotal_SBR_15`, `heattotal_REF`
  - Description: Contains heat release data over time (in hours) for different material samples (EVA, SA, SBR) at 0.5 and 1.5 concentrations, plus a reference (REF).
- **Sheet: Tabelle1**
  - Columns: `time [h]`, `Unnamed: 1` (renamed to `d`), `heattotal_EVA_15`, `heattotal_SA_15`, `heattotal_SBR_15`, `heattotal_REF`, `PCS_EVA15 (20°C)`, `PCS_SA15 (20°C)`, `PCS_SBR15 (20°C)`, `PCS_REF (20°C)`, `PCS_EVA15 (60°C)`, `PCS_SA15 (60°C)`, `PCS_SBR15 (60°C)`, `PCS_REF (60°C)`
  - Description: Contains heat release and PCS data over time (in days) for materials at 1.5 concentration, plus PCS measurements at 20°C and 60°C.

### 2. `20C_PCC_HeatRelease_All_28d_Alex.xlsx`
- **Sheet: Tabelle2**
  - Columns: `time`, `heattotal_EVA_15`, `heattotal_SA_15`, `heattotal_SBR_15`, `heattotal_REF`, `PCS_EVA15 (20°C)`, `PCS_SA15 (20°C)`, `PCS_SBR15 (20°C)`, `PCS_REF (20°C)`, `PCS_EVA15 (60°C)`, `PCS_SA15 (60°C)`, `PCS_SBR15 (60°C)`, `PCS_REF (60°C)`
  - Description: Contains heat release and PCS data over time for materials at 1.5 concentration, with PCS measurements at 20°C and 60°C.

## Script Functionality
The script performs the following tasks:

### 1. Data Loading and Cleaning
- Loads data from the specified Excel files and sheets using `pandas`.
- Renames columns in `Tabelle1` (`time` to `time [h]`, `Unnamed: 1` to `d`) and drops the first row for consistency.
- Displays basic data information (`head`, `info`, `describe`) for each dataset.

### 2. Visualizations
- **First Sheet (`HeatRelease.xlsx`, `HeatRelease`)**:
  - Plots heat release vs. time (hours) for all samples (EVA_05, EVA_15, SA_05, SA_15, SBR_05, SBR_15, REF) in a single plot.
  - Creates separate plots for EVA (0.5, 1.5), SA (0.5, 1.5), SBR (0.5, 1.5), and REF.
  - Saves plots to the `First Sheet` directory:
    - `HeatRelease.png`
    - `HeatRelease EVA.png`
    - `HeatRelease SA.png`
    - `HeatRelease SBR.png`
    - `HeatRelease REF.png`

- **Second Sheet (`HeatRelease.xlsx`, `Tabelle1`)**:
  - Plots heat release vs. time (days) for EVA_15, SA_15, SBR_15, and REF.
  - Plots PCS vs. time (days) at 20°C and 60°C for EVA_15, SA_15, SBR_15, and REF.
  - Saves plots to the `Second Sheet` directory:
    - `HeatRelease.png`
    - `pcs_20C.png`
    - `pcs_60C.png`

- **Third Sheet (`HeatRelease.xlsx`, `Tabelle2`)**:
  - Plots heat release vs. time for EVA_15, SA_15, SBR_15, and REF.
  - Plots PCS vs. time at 20°C and 60°C for EVA_15, SA_15, SBR_15, and REF.
  - Saves plots to the `Third Sheet` directory:
    - `HeatRelease.png`
    - `pcs_20C.png`
    - `pcs_60C.png`

## Usage
1. Ensure the Excel files (`HeatRelease.xlsx` and `20C_PCC_HeatRelease_All_28d_Alex.xlsx`) are in the same directory as the script.
2. Create `First Sheet`, `Second Sheet`, and `Third Sheet` directories in the working directory to store output plots.
3. Run the script in a Python environment (e.g., Jupyter Notebook or a Python IDE).
4. The script will generate and save visualizations as PNG files in the respective directories.

Example command to run the script (if saved as `heat_release_analysis.py`):
```bash
python heat_release_analysis.py
```

## Notes
- The script assumes the Excel files have the specified sheet names and column structures. Verify the file format if errors occur.
- The `%matplotlib inline` command is included for Jupyter Notebook compatibility. Remove it if running in a different environment.
- Visualizations use specific figure sizes, colors, and axis labels for clarity, which can be modified as needed.
- Ensure the `First Sheet`, `Second Sheet`, and `Third Sheet` directories exist before running the script to avoid file-saving errors.

## Output Files
- **First Sheet**:
  - `HeatRelease.png`: Combined heat release plot for all samples.
  - `HeatRelease EVA.png`: Heat release for EVA_05 and EVA_15.
  - `HeatRelease SA.png`: Heat release for SA_05 and SA_15.
  - `HeatRelease SBR.png`: Heat release for SBR_05 and SBR_15.
  - `HeatRelease REF.png`: Heat release for REF.
- **Second Sheet**:
  - `HeatRelease.png`: Heat release for EVA_15, SA_15, SBR_15, and REF.
  - `pcs_20C.png`: PCS at 20°C for EVA_15, SA_15, SBR_15, and REF.
  - `pcs_60C.png`: PCS at 60°C for EVA_15, SA_15, SBR_15, and REF.
- **Third Sheet**:
  - `HeatRelease.png`: Heat release for EVA_15, SA_15, SBR_15, and REF.
  - `pcs_20C.png`: PCS at 20°C for EVA_15, SA_15, SBR_15, and REF.
  - `pcs_60C.png`: PCS at 60°C for EVA_15, SA_15, SBR_15, and REF.