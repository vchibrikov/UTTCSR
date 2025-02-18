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

On the next step, you can use the controls to adjust the smoothing parameters (window length and polynomial order). Basic window length and polynomial order was asigned as 50 and 1, respectively, being adjusted to data. Overfitting and underfitting curves are presented on Figures 3 and 4. Plotting of only original/smoothed data is possible by clicking respected parameters on a righthand toolbar (Figures 5 and 6). 

### Figure 3 - Example of smoothing underfit.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 51 44" src="https://github.com/user-attachments/assets/9d8f140b-460c-4a3d-990e-9f752371ccba" />

### Figure 4 - Example of smoothing overfit.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 52 04" src="https://github.com/user-attachments/assets/b9db4fe3-99c8-4356-a28e-c1260de83146" />

### Figure 5 - Example of original data curve plotted only.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 53 28" src="https://github.com/user-attachments/assets/c8a7d7d6-3205-4de4-97be-7132b0aa6bd1" />

### Figure 6 - Example of smoothed data curve plotted only.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 53 24" src="https://github.com/user-attachments/assets/19847780-29df-4949-b343-198553bac0dd" />

On the next step, start (Figures 7-8), elastic limit (Figures 9), and end (Figures 10-11) points for the material's elongation-force curves should be defined.

### Figure 7 - Pop-up window informing introduction of start point of an elongation-force curve.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 52 14" src="https://github.com/user-attachments/assets/00d5151c-54de-496c-8740-6588e9394212" />

### Figure 8 - Elongation-force curve with starting point defined.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 52 33" src="https://github.com/user-attachments/assets/8f8b416d-a81a-48a7-af44-06de791cc536" />

### Figure 9 - Pop-up window informing introduction of elastic limit point of an elongation-force curve.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 52 38" src="https://github.com/user-attachments/assets/ae9d5770-c09c-415b-8896-519d2a416fe4" />

### Figure 10 - Pop-up window informing introduction of an end point of an elongation-force curve.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 52 47" src="https://github.com/user-attachments/assets/69263759-8af5-430d-846d-6ba35df8af06" />


### Figure 11 - Elongation-force curve with an end point defined.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 52 58" src="https://github.com/user-attachments/assets/d22625cf-decc-4bd0-bd15-2f2fa7ee508c" />

After defining the critical points, click the "Calculate" button to compute the mechanical properties: slope_1: slope of elastic deformation; slope_2: slope of plastic deformation; elongation_at_start_mm: value of elongation at the curve start; force_at_start_N: value of force at the curve start; elongation_at_elastic_limit_mm: value of elongation at the elasto-plastic transition point; force_at_elastic_limit_N: value of force at elasto-plastic transition point; maximum_elongation_mm: value of elongation at maximum force; maximum_force_N: maximum force achieved during measurement; toughness_N_mm: material toughness as an area under the elongation-force curve. Results will be displayed in a message box (Figure 12) and saved to uttcsr_output.xlsx Excel file.

### Figure 12 - Pop-up window with a results of data calculation.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 53 03" src="https://github.com/user-attachments/assets/314ce80f-3c54-42dc-8960-7ebff6e70b08" />

If you loaded multiple .MTR files, you can navigate between curves using the "Next" and "Previous" buttons (Figure 13).

### Figure 13 - Plotting of the following curve after pressing "Next" button.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 53 18" src="https://github.com/user-attachments/assets/cfcc25ec-c810-4df0-9019-9dca88826969" />

The calculated results for each file are saved in an Excel sheet (Figure 14). The following data is recorded for each curve: filename; slope_1; slope_2; elongation_at_start_mm; force_at_start_N; elongation_at_elastic_limit_mm; force_at_elastic_limit_N; maximum_elongation_mm; maximum_force_N; toughness_N_mm. Explanatory elongation-force curve is provided on Figure 15.

### Figure 14 - Example of uttcsr_output.xlsx sheet.
<img width="1728" alt="Знімок екрана 2025-02-17 о 15 55 45" src="https://github.com/user-attachments/assets/6e07bdba-76ab-457f-a4a7-99889dc5b088" />

### Figure 15 - Explanatory elongation-force curve with a calculated parameters visualized.
![FIG_15](https://github.com/user-attachments/assets/71ca4cc0-ff39-47ff-a9d2-fdae3be05740)

## License
This project is licensed under the MIT License - see the LICENSE file for details.

> For any issues or feature requests, feel free to open an issue in this repository.
