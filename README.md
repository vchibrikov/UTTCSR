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

### Figure 1 - Importing .MTR datafiles
<img width="781" alt="1" src="https://github.com/user-attachments/assets/1ffe5c52-7239-484b-a5e8-128fa0dbfee9" />

The force-elongation curve will be displayed in a Tkinter window (Figure 2).

### Figure 1 - Importing .MTR datafiles

