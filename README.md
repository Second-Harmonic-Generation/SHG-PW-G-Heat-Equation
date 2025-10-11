## 🧰 How to Use This Template    

Click the green **"Use this template"** button at the top of the page, then choose **"Create a new repository"**.   

This will create your own copy of this project, which you can modify freely — no need to fork!   

 
<p align="center">
  <img src="./images/SHG-banner.png" alt="SHG Logo">
</p>


<h1 align="center">SHG-CW-G-Heat-Equation</h1>

<div align="center">

| **Term** | **Definition** |
|----------|----------------|
| **SHG** | Second Harmonic Generation |
| **CW** | Continuous Wave |
| **G** | Gaussian |
</div>

&nbsp;

<div align="center">

Article title:       
**Temperature Distribution in a Gaussian End-Pumped Nonlinear KTP Crystal: the Temperature Dependence of Thermal Conductivity and Radiation Boundary Condition**
</div>

&nbsp;

---

***Table of Contents***

<div>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#1-about-this-repository"><i><b>1. About this repository</b></i></a>
</div>
&nbsp;

<div>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#2-getting-started"><i><b>2. Getting Started</b></i></a>
</div>
&nbsp;

<div>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#3-how-to-cite-us"><i><b>3. How to Cite Us</b></i></a>
</div>
&nbsp;


<div>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#4-contact-information"><i><b>4. Contact Information</b></i></a>
</div>
&nbsp;

---    

## 1. About this repository


This repository contains the research article **“Temperature Distribution in a Gaussian End-Pumped Nonlinear KTP Crystal: the Temperature Dependence of Thermal Conductivity and Radiation Boundary Condition”**, together with supporting source code, numerical results, and reproducibility assets.  


Continuous-wave (CW) second harmonic generation in nonlinear crystals is strongly affected by heat dissipation. This work analyzes the **transient temperature distribution** in a KTP crystal under Gaussian end-pumping by solving the nonlinear, inhomogeneous heat equation. Unlike many earlier models, the study incorporates:  

- **Temperature-dependent thermal conductivity** of KTP  
- **Convective and radiative boundary conditions** at crystal surfaces  

A finite difference method (FDM) solver was implemented to numerically evaluate the system. Results show that neglecting thermal conductivity variations leads to significant temperature prediction errors, and while radiative effects are negligible in thin crystals, they become relevant for larger geometries with wide pump beams. These findings improve modeling accuracy for **thermal lensing, phase mismatching, and efficiency reduction** in nonlinear optical systems.  


```
Folder PATH listing
+---citation                      <-- Contains citation materials and papers
│       1_Heat-Equation_Continu…  <-- Heat equation analytical paper
│       2_Heat-Equation_Continu…  <-- Heat equation continuous wave paper
│       3_Heat-Equation_Pulsed-…  <-- Heat equation pulsed wave paper
│       4_Phase-Mismatch_Pulsed…  <-- Phase mismatch pulsed wave paper
│       5_Ideal_Continuous-Wave…  <-- Ideal continuous wave paper
│       6_Ideal_Pulsed-Wave_Be…   <-- Ideal pulsed wave Bessel paper
│       7_Coupled_Continuous-Wa…  <-- Coupled continuous wave paper
│       README.md                 <-- Citation guidelines and information
│
+---images                        <-- Contains project images and logos
│       SHG-banner.png            <-- SHG project banner
│
+---results                       <-- Numerical simulation results
│       ST_085_time_1_T_r.plt     <-- Radial temperature data
│       ST_085_time_1_T_t.plt     <-- Transverse temperature data
│       ST_085_time_1_T_z.plt     <-- Axial temperature data
│
+---src                           <-- Contains source code
│       Code_SHG-CW-G-Heat-Equ…   <-- Fortran finite difference solver
│
│       Article_SHG-CW-G-Heat-…   <-- Main research paper PDF
│       CITATION.cff              <-- Citation metadata file
│       LICENSE                   <-- Project license information
│       README.md                 <-- Project overview and documentation
│

```

## 2. Getting Started

### 2.1. Prerequisites
- **Fortran Compiler** (gfortran, Intel Fortran, or similar)
- **Text Editor** (VS Code, Cursor, or any Fortran-capable editor)
- **PDF Reader** (for accessing research papers)
- **Git** (for cloning the repository)

### 2.2. Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/Second-Harmonic-Generation/SHG-CW-G-Heat-Equation.git
   cd SHG-CW-G-Heat-Equation
   ```

2. **Explore the Research Papers**
   - Navigate to the `citation/` folder
   - Read the main research paper: `Article_SHG_Continuous-Wave_Gaussian_Heat-Equation.pdf`
   - Review additional papers for comprehensive understanding

3. **Compile and Run the Fortran Code**
   ```bash
   cd src
   gfortran -o heat_equation 2_Heat-Equation_Continuous-Wave_Gaussian.f90
   ./heat_equation
   ```

4. **Analyze Results**
   - Check the `results/` folder for output files
   - Examine `.plt` files for temperature distribution data
   - Use plotting software (Gnuplot, Python matplotlib, etc.) to visualize results

5. **Modify Parameters** (Optional)
   - Edit the Fortran source code to change simulation parameters
   - Recompile and run to explore different scenarios
   - Compare results with published findings

---


## 3. How to Cite Us
Please refer to the [**citation**](./citation/) folder for accurate citations. It contains essential guidelines for accurate referencing, ensuring accurate acknowledgement of our work.


  
## 4. Contact Information

For questions not addressed in the resources above, please connect with [Mostafa Rezaee](https://www.linkedin.com/in/mostafa-rezaee/) on LinkedIn for personalized assistance.
