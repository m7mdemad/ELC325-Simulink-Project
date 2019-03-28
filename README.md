# **MATLAB Simulink - Communication Toolbox**
Simulation and performance evaluation of the following modulation schemes in an Additive White Gaussian Noise (AWGN) envrionment:
- **Binary Phase-Shift Keying (BPSK)**
- **Quadrature Phase-Shift Keying (QPSK)**
- **Frequency Shift Keying (FSK)**
- **Quadrature Amplitude Modulation (QAM)**
---

# Common steps to reproduce the simulation model:
- Open MATLAB, run the "simulink" command from the command window. 
- In the Simulink window, click on "New Model"
- Click on "Library Browser" and drag and drop the required blocks:
    * Modulator Baseband (Scheme Dependent)
    * Demodulator Baseband (Scheme Dependent)
    * Random Integer Generator
    * AWGN channel 
    * Raised Cosine Transmit Filter
    * Raised Cosine Receive Filter
    * Constellation Diagram (x2)
    * Error Rate Calculation
    * Display
    * To Workspace
- Connect the blocks as shown in the screenshots using drag and drop.
- Set the simulation period to 100000. *(With Raised Cosine Filters, it was set to 10000)*
- Save the model using Ctrl+S

Note: Scatter plots are produced at a noise level of 10 dB.

# Common steps to reproduce the simulation model:
- Run the "bertool" command from the MATLAB command window.
- In the BER Tool window, set the E<sub>b</sub>/N<sub>0</sub> range to -10:10
- Choose the modulation scheme from the dropdown list and click "Plot"
- Open Monte Carlo tab, set the E<sub>b</sub>/N<sub>0</sub> range to -10:10
- Choose the model file using the "Browse" button and click "Run"

---
# **Binary Phase-Shift Keying Modulation (BPSK)**
## Definition
BPSK is a modulation scheme which shifts the phase of the output signal depending on the input. The input is binary and the 0’s and 1’s are represented by two different phase states in the carrier signal. The phase difference is 180 degrees.

## Specific step:
- Click on the Random Integer Generator block and set the set size to 2

## Without Raised Cosine Filter:
### Simulink Model Diagram:
![Simulink Model Diagram](/BPSK/Simulink\ Model.png)
### Scatter Plot (Before Noise)
![Scatter Plot (Before Noise)](/BPSK/Scatter\ Plot\ (Before\ Noise).png)
### Scatter Plot (After Noise)
![Scatter Plot (Before Noise)](/BPSK/Scatter\ Plot\ (After\ Noise).png)
### BER Performance Plot
![BER Performance Plot](/BPSK/BER\ Performance.png)


## With Raised Cosine Filter:
### Simulink Model Diagram:
![Simulink Model Diagram](/BPSK\_RC/Simulink\ Model.png)
### Scatter Plot (Before Noise)
![Scatter Plot (Before Noise)](/BPSK\_RC/Scatter\ Plot\ (Before\ Noise).png)
### Scatter Plot (After Noise)
![Scatter Plot (Before Noise)](/BPSK\_RC/Scatter\ Plot\ (After\ Noise).png)
### BER Performance Plot
![BER Performance Plot](/BPSK\_RC/BER\ Performance.png)