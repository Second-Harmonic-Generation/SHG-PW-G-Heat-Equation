## 🧰 How to Use This Template    

Click the green **"Use this template"** button at the top of the page, then choose **"Create a new repository"**.   

This will create your own copy of this project, which you can modify freely — no need to fork!   

 
<p align="center">
  <img src="./images/SHG-banner.png" alt="SHG Logo">
</p>


<h1 align="center">SHG-PW-G-Heat-Equation</h1>

<div align="center">

| **Term** | **Definition** |
|----------|----------------|
| **SHG** | Second Harmonic Generation |
| **PW** | Pulsed Wave |
| **G** | Gaussian |
</div>

&nbsp;

<div align="center">

Article title:       
**Complete Anisotropic Time-Dependent Heat Equation in KTP Crystal under Repetitively Pulsed Gaussian Beams: A Numerical Approach**
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


This repository contains the **toolkit and computational tools** used in the research article **"Complete Anisotropic Time-Dependent Heat Equation in KTP Crystal under Repetitively Pulsed Gaussian Beams: A Numerical Approach"** (Applied Optics, 2015), including source code, numerical solvers, and reproducibility assets.  


This toolkit provides computational tools for analyzing **transient temperature distribution** in cylindrical nonlinear potassium titanyl phosphate (KTP) crystals under repetitively pulsed Gaussian pumping sources. The toolkit implements a thorough and detailed solution for the time-dependent heat equation using advanced modeling features that are often neglected in simpler approaches:  

- **Temperature-dependent thermal conductivity** of KTP crystal  
- **Convective and radiative boundary conditions** at crystal surfaces  
- **Finite difference time domain (FDTD) method** for numerical calculations  

The research demonstrates that the radiation term has a negligible effect and can be safely ignored, while the temperature dependence of thermal conductivity is more influential. Ignoring temperature-dependent thermal conductivity introduces significant errors into the modeling. The toolkit shows the time evolution of temperature as the crystal is pumped with a train of successive Gaussian pulses until reaching thermal equilibrium. These tools improve modeling accuracy for **thermal lensing, phase mismatching, and efficiency reduction** in nonlinear optical systems, particularly in second harmonic generation applications.  


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
│       E_009_f_500_Np_10_tp_50…  <-- Thermal conductivity radial data
│       E_009_f_500_Np_10_tp_50…  <-- Thermal conductivity transverse data
│       E_009_f_500_Np_10_tp_50…  <-- Thermal conductivity axial data
│       E_009_f_500_Np_10_tp_50…  <-- Temperature radial data
│       E_009_f_500_Np_10_tp_50…  <-- Temperature transverse data
│       E_009_f_500_Np_10_tp_50…  <-- Temperature axial data
│
+---src                           <-- Contains source code
│       Code_SHG_PW_G_Heat-Equ…   <-- Fortran finite difference solver
│
│       Article_SHG-PW-G-Heat-…   <-- Main research paper PDF
│       CITATION.cff              <-- Citation metadata file
│       LICENSE                   <-- Project license information
│       README.md                 <-- Project overview and documentation
│

```

## 2. Getting Started

### 2.1. Prerequisites

#### 2.1.1. Required Software
- **Fortran Compiler**: gfortran (GNU), Intel Fortran, or similar
- **Text Editor**: VS Code, Cursor, or any Fortran-capable editor
- **PDF Reader**: For accessing research papers
- **Git**: For cloning the repository
- **Plotting Software**: Gnuplot, Python matplotlib, or similar for result visualization

#### 2.1.2. System Requirements
- **Operating System**: Linux, macOS, or Windows (with WSL)
- **Memory**: Minimum 4GB RAM (8GB recommended)
- **Storage**: ~100MB for repository and results
- **Processing**: Any modern CPU (execution time ~1 minute)

### 2.2. Installation and Setup

#### 2.2.1. Clone the Repository
```bash
git clone https://github.com/Second-Harmonic-Generation/SHG-PW-G-Heat-Equation.git
cd SHG-PW-G-Heat-Equation
```

#### 2.2.2. Verify Fortran Compiler
```bash
# Check if gfortran is installed
gfortran --version

# If not installed (Ubuntu/Debian):
sudo apt-get install gfortran

# If not installed (macOS with Homebrew):
brew install gcc
```

### 2.3. Running the Simulation

#### 2.3.1. Compile the Fortran Code
```bash
cd src
gfortran -O2 -o heat_equation Code_SHG_PW_G_Heat-Equation.f90
```

**Alternative compilation options:**
```bash
# With Intel Fortran (if available):
ifort -O2 -o heat_equation Code_SHG_PW_G_Heat-Equation.f90

# With debugging information:
gfortran -g -O0 -o heat_equation Code_SHG_PW_G_Heat-Equation.f90

# With maximum optimization:
gfortran -O3 -march=native -o heat_equation Code_SHG_PW_G_Heat-Equation.f90
```

#### 2.3.2. Execute the Simulation
```bash
./heat_equation
```

**Expected output:**
- Console display of simulation parameters
- Progress indication during execution
- Confirmation of result file generation

### 2.4. Understanding the Results

#### 2.4.1. Output Files
The simulation generates six `.plt` files in the `src/` directory:

| File Type | Description | Content |
|-----------|-------------|---------|
| `*_T_t.plt` | Temperature vs. Time | Temporal evolution at crystal center |
| `*_T_r.plt` | Temperature vs. Radius | Radial temperature distribution |
| `*_T_z.plt` | Temperature vs. Position | Axial temperature distribution |
| `*_K_t.plt` | Thermal Conductivity vs. Time | Temporal evolution of k(T) |
| `*_K_r.plt` | Thermal Conductivity vs. Radius | Radial k(T) distribution |
| `*_K_z.plt` | Thermal Conductivity vs. Position | Axial k(T) distribution |

#### 2.4.2. Data Format
Each `.plt` file contains two columns:
- **Column 1**: Independent variable (time, radius, or position)
- **Column 2**: Dependent variable (temperature or thermal conductivity)

#### 2.4.3. Visualization Options

**Using Gnuplot:**
```bash
# Install Gnuplot
sudo apt-get install gnuplot  # Ubuntu/Debian
brew install gnuplot          # macOS

# Plot temperature vs. time
gnuplot -e "plot 'E_009_f_500_Np_10_tp_50_T_t.plt' with lines; pause -1"
```

**Using Python matplotlib:**
```python
import numpy as np
import matplotlib.pyplot as plt

# Load data
data = np.loadtxt('E_009_f_500_Np_10_tp_50_T_t.plt')
time, temperature = data[:, 0], data[:, 1]

# Plot
plt.figure(figsize=(10, 6))
plt.plot(time, temperature)
plt.xlabel('Time (s)')
plt.ylabel('Temperature (K)')
plt.title('Temperature Evolution at Crystal Center')
plt.grid(True)
plt.show()
```

### 2.5. Customizing Parameters

#### 2.5.1. Modifying Simulation Parameters
Edit the following section in `Code_SHG_PW_G_Heat-Equation.f90` (lines 100-109):

```fortran
! For Calculation
E = 0.09        ! Pulse energy (J)
Np = 10         ! Number of pulses
tp = 50e-6      ! Pulse duration (s)
freq = 500      ! Repetition frequency (Hz)

! For Generating Filenames
EE = '009'      ! Energy string (for filename)
Npf = '10'      ! Number of pulses string
tpf = '50'      ! Pulse duration string
freqf = '500'   ! Frequency string
```

#### 2.5.2. Physical Parameters
Modify crystal and beam parameters (lines 156-184):

```fortran
h = 10.                 ! Heat transfer coefficient (W/(m²·K))
T0 = 300.               ! Initial temperature (K)
Cp = 728.016            ! Heat capacity (J/(kg·K))
kT0 = 13.               ! Thermal conductivity at T₀ (W/(m·K))
roh = 2945.             ! Mass density (kg/m³)
gama = 0.1              ! Absorption coefficient (1/m)
omegaf = 100.e-6        ! Beam waist (m)
length = 0.02           ! Crystal length (m)
radius = 5e-3           ! Crystal radius (m)
```

### 2.6. Troubleshooting

#### 2.6.1. Common Issues

**Compilation Errors:**
- Ensure Fortran compiler is properly installed
- Check for syntax errors in the source code
- Verify file permissions

**Runtime Errors:**
- Check available memory (simulation requires ~100MB)
- Ensure output directory is writable
- Verify numerical stability (check stability parameter output)

**Performance Issues:**
- Use optimization flags (`-O2` or `-O3`)
- Close unnecessary applications to free memory
- Consider reducing grid resolution for faster execution

#### 2.6.2. Getting Help
- Review the main research paper for theoretical background
- Check the citation folder for related publications
- Contact the authors for technical support

---


## 3. How to Cite Us
Please refer to the [**citation**](./citation/) folder for accurate citations. It contains essential guidelines for accurate referencing, ensuring accurate acknowledgement of our work.


  
## 4. Contact Information

For questions not addressed in the resources above, please connect with [Mostafa Rezaee](https://www.linkedin.com/in/mostafa-rezaee/) on LinkedIn for personalized assistance.
