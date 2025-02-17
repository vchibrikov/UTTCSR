# UTTCSR
UTTCSR (Uniaxial Tensile Tests with Constant Strain Rate) - repository of Python and R scripts for tensile test data processing, analysis and visualization. Scripts allows to plot and smooth input data, evaluate slopes of Young's and strain hardening moduli, forces/stresses and elongations/strains at various stages (start, elastic limit, maximum). 
Code written for the project entitled "3D Printing of Plant Cell Wall-Inspired Biomaterials", supported by the National Science Center, Poland (grant nr - 2023/49/B/NZ9/02979). More information of project: https://projekty.ncn.gov.pl/index.php?projekt_id=591903

## Features
- Load .MTR files and display force-elongation curves
- Apply Savitzky-Golay smoothing filter to force-elongation data
- Define critical points (start, elastic limit, and end) interactively on the plot
- Calculate mechanical properties:
  - slope of elastic deformation
  - slope of plastic deformation
  - start/elastic limit/maximum forces and elongations
  - toughness
- Display results in a user-friendly message box
- Save results to an Excel file (uttcsr_output.xlsx)

## Requirements
- Python libraries:
  - pandas
  - numpy
  - matplotlib
  - scipy
  - openpyxl
  - tkinter
- Visual Studio Code release: 1.93.1
- Python release: 3.12.4. 64-bit

> Warning! There are no guaranties this code will run on your machine.

## Usage
Upon launching the application, you will be prompted to select one or more .MTR files (Figure 1). These files should contain force vs. elongation data with the first 19 rows containing metadata (optimized for Deben tensile tester).

### Figure 1 - Importing .MTR datafiles.
<img width="781" alt="1" src="https://github.com/user-attachments/assets/1ffe5c52-7239-484b-a5e8-128fa0dbfee9" />

The force-elongation curve will be displayed in a Tkinter window (Figure 2).

### Figure 2 - Main screenview representing data curve (blue), smoothed curve (red), and adjustment parameters (righthand).
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 51 16" src="https://github.com/user-attachments/assets/e67936e0-4704-4190-bd31-83aec48816df" />

On the next step, you can use the controls to adjust the smoothing parameters (window length and polynomial order). Basic window length and polynomial order was asigned as 50 and 1, respectively, being adjusted to data. Overfitting and underfitting curves are presented on Figures 3 and 4.

### Figure 3 - Example of smoothing overfit.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 51 44" src="https://github.com/user-attachments/assets/9d8f140b-460c-4a3d-990e-9f752371ccba" />

### Figure 4 - Example of smoothing underfit.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 52 04" src="https://github.com/user-attachments/assets/b9db4fe3-99c8-4356-a28e-c1260de83146" />


