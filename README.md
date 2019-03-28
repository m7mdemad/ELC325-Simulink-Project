# **MATLAB Simulink - Communication Toolbox**
Simulation and performance evaluation of the following modulation schemes in an Additive White Gaussian Noise (AWGN) envrionment:
- **Binary Phase-Shift Keying (BPSK)**
- **Quadrature Phase-Shift Keying (QPSK)**
- **Frequency Shift Keying (FSK)**
- **Quadrature Amplitude Modulation (QAM)**
---

# Common steps to reproduce the simulation model:
- Open MATLAB, run the "simulink" command from the command window. 
- In the Simulink window, click on "New Model".
- Click on "Library Browser" and drag and drop the required blocks:
    * Modulator Baseband (Scheme Dependent)
    * Demodulator Baseband (Scheme Dependent)
    * Random Integer Generator (See Note 1)
    * AWGN channel (set noise level to EbNo)
    * Raised Cosine Transmit Filter
    * Raised Cosine Receive Filter
    * Constellation Diagram (x2)
    * Error Rate Calculation
    * Display
    * To Workspace (set the name to "ber")
- Connect the blocks as shown in the screenshots using drag and drop.
- Set the simulation period to 100000 *(With Raised Cosine Filters, it was set to 10000)*. 
- For QAM, there are more steps in the QAM section.
- Save the model using Ctrl+S.



# Common steps to reproduce the simulation model:
- Run the "bertool" command from the MATLAB command window.
- In the BER Tool window, set the E<sub>b</sub>/N<sub>0</sub> range to -10:10
- Choose the modulation scheme from the dropdown menu
- Set the modulation index (See Note 2) and click "Plot"
- Open the Monte Carlo tab, set the E<sub>b</sub>/N<sub>0</sub> range to -10:10
- Set the variable name to "ber"
- Choose the model file using the "Browse" button and click "Run"

Note 1: Random Generator Set Size and Modulation Index should be set to the same value for each scheme. BPSK/FSk: 2, QPSK: 4, QAM: 16 or 64.

Note 2: Scatter plots are produced at a noise level of 10 dB.

Note 3: This project was created using MATLAB R2016a. Unless otherwise stated, all values are left to the default setting (e.g. Initial Seed in the AWGN Channel block is set to 67) 

---
# **Binary Phase-Shift Keying Modulation (BPSK)**
## Explanation
BPSK is a modulation scheme which shifts the phase of the output signal depending on the input. The input is binary and the 0’s and 1’s are represented by two different phase states in the carrier signal. The phase difference is 180 degrees.


## BPSK without Raised Cosine Filter
### Simulink Model Diagram:
![Simulink Model Diagram](/BPSK/Model.png)
### Scatter Plot (Before Noise)
![Scatter Plot (Before Noise)](/BPSK/ScatterPlot(BeforeNoise).png)
### Scatter Plot (After Noise)
![Scatter Plot (Before Noise)](/BPSK/ScatterPlot(AfterNoise).png)
### BER Performance Plot
![BER Performance Plot](/BPSK/BER-Plot.png)


## BPSK with Raised Cosine Filter
### Simulink Model Diagram:
![Simulink Model Diagram](/BPSK-RC/Model.png)
### Scatter Plot (Before Noise)
![Scatter Plot (Before Noise)](/BPSK-RC/ScatterPlot(BeforeNoise).png)
### Scatter Plot (After Noise)
![Scatter Plot (Before Noise)](/BPSK-RC/ScatterPlot(AfterNoise).png)
### BER Performance Plot
![BER Performance Plot](/BPSK-RC/BER-Plot.png)
___
# **Quadrature Phase-Shift Keying Modulation (QPSK)**
## Explanation
QPSK is a version of PSK in which two bits are modulated at once, selecting one of four possible carrier phase shifts (0&deg;, 90&deg;, 180&deg;, or 270&deg;). QPSK doubles the bandwidth efficiency.

## QPSK without Raised Cosine Filter
### Simulink Model Diagram:
![Simulink Model Diagram](/QPSK/Model.png)
### Scatter Plot (Before Noise)
![Scatter Plot (Before Noise)](/QPSK/ScatterPlot(BeforeNoise).png)
### Scatter Plot (After Noise)
![Scatter Plot (Before Noise)](/QPSK/ScatterPlot(AfterNoise).png)
### BER Performance Plot
![BER Performance Plot](/QPSK/BER-Plot.png)


## QPSK with Raised Cosine Filter
### Simulink Model Diagram:
![Simulink Model Diagram](/QPSK-RC/Model.png)
### Scatter Plot (Before Noise)
![Scatter Plot (Before Noise)](/QPSK-RC/ScatterPlot(BeforeNoise).png)
### Scatter Plot (After Noise)
![Scatter Plot (Before Noise)](/QPSK-RC/ScatterPlot(AfterNoise).png)
### BER Performance Plot
![BER Performance Plot](/QPSK-RC/BER-Plot.png)
___
# **Frequency Shift Keying (FSK)**
## Explanation
FSK is a scheme in which digital bit streams are transmitted through discrete frequency shifts of a carrier signal.

## FSK without Raised Cosine Filter
### Simulink Model Diagram:
![Simulink Model Diagram](/FSK/Model.png)
### Scatter Plot (Before Noise)
![Scatter Plot (Before Noise)](/FSK/ScatterPlot(BeforeNoise).png)
### Scatter Plot (After Noise)
![Scatter Plot (Before Noise)](/FSK/ScatterPlot(AfterNoise).png)
### BER Performance Plot
![BER Performance Plot](/FSK/BER-Plot.png)


## FSK with Raised Cosine Filter
### Simulink Model Diagram:
![Simulink Model Diagram](/FSK-RC/Model.png)
### Scatter Plot (Before Noise)
![Scatter Plot (Before Noise)](/FSK-RC/ScatterPlot(BeforeNoise).png)
### Scatter Plot (After Noise)
![Scatter Plot (Before Noise)](/FSK-RC/ScatterPlot(AfterNoise).png)
### BER Performance Plot
![BER Performance Plot](/FSK-RC/BER-Plot.png)
___

# **Quadrature Amplitude Modulation (QAM)**
## Explanation
QAM is a scheme used to transmit two digital bit streams or two analog signals by modulating the amplitudes of two carrier waves so that they differ in phase by 90&deg;. The two signals can be mathematically represented by a sine and a cosine wave.

## Extra simulation steps
- Click on the QAM Modulator Baseband block
- Set the M-ary number to 16 or 64
- Set the Normalization method to Average Power


## QAM-16 without Raised Cosine Filter
### Simulink Model Diagram:
![Simulink Model Diagram](/QAM16/Model.png)
### Scatter Plot (Before Noise)
![Scatter Plot (Before Noise)](/QAM16/ScatterPlot(BeforeNoise).png)
### Scatter Plot (After Noise)
![Scatter Plot (Before Noise)](/QAM16/ScatterPlot(AfterNoise).png)
### BER Performance Plot
![BER Performance Plot](/QAM16/BER-Plot.png)


## QAM-16 with Raised Cosine Filter
### Simulink Model Diagram:
![Simulink Model Diagram](/QAM16-RC/Model.png)
### Scatter Plot (Before Noise)
![Scatter Plot (Before Noise)](/QAM16-RC/ScatterPlot(BeforeNoise).png)
### Scatter Plot (After Noise)
![Scatter Plot (Before Noise)](/QAM16-RC/ScatterPlot(AfterNoise).png)
### BER Performance Plot
![BER Performance Plot](/QAM16-RC/BER-Plot.png)


## QAM-64 without Raised Cosine Filter
### Simulink Model Diagram:
![Simulink Model Diagram](/QAM64/Model.png)
### Scatter Plot (Before Noise)
![Scatter Plot (Before Noise)](/QAM64/ScatterPlot(BeforeNoise).png)
### Scatter Plot (After Noise)
![Scatter Plot (Before Noise)](/QAM64/ScatterPlot(AfterNoise).png)
### BER Performance Plot
![BER Performance Plot](/QAM64/BER-Plot.png)


## QAM-64 with Raised Cosine Filter
### Simulink Model Diagram:
![Simulink Model Diagram](/QAM64-RC/Model.png)
### Scatter Plot (Before Noise)
![Scatter Plot (Before Noise)](/QAM64-RC/ScatterPlot(BeforeNoise).png)
### Scatter Plot (After Noise)
![Scatter Plot (Before Noise)](/QAM64-RC/ScatterPlot(AfterNoise).png)
### BER Performance Plot
![BER Performance Plot](QAM64-RC/BER-Plot.png)
