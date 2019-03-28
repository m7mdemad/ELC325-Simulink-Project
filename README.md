# Digital Communications MATLAB Simulink Project
Simulation and performance evaluation of the following modulation schemes in an Additive White Gaussian Noise (AWGN) envrionment:
- **Binary Phase-Shift Keying (BPSK)**
- **Quadrature Phase-Shift Keying (QPSK)**
- **Frequency Shift Keying (FSK)**
- **Quadrature Amplitude Modulation (QAM)**
---

# Common steps to reproduce the simulation model:
- Open MATLAB, run the ```simulink``` command from the command window. 
- In the Simulink window, click on ```New Model```.
- Click on ```Library Browser``` and drag and drop the required blocks:
    * Modulator Baseband (Scheme Dependent)
    * Demodulator Baseband (Scheme Dependent)
    * ```Random Integer Generator``` (See Note 1)
    * ```AWGN channel``` (set noise level to ```EbNo```)
    * ```Raised Cosine Transmit Filter```
    * ```Raised Cosine Receive Filter```
    * ```Constellation Diagram``` (x2)
    * ```Error Rate Calculation```
    * ```Display```
    * ```To Workspace``` (set the name to ```ber```)
- Connect the blocks as shown in the screenshots using drag and drop.
- Set the ```Simulation period``` to ```100000``` *(With Raised Cosine Filters, it was set to ```10000```)*. 
- For QAM, there are more steps in the QAM section.
- Save the model using ```Ctrl+S```.



# Common steps to reproduce the simulation model:
- Run the ```bertool``` command from the MATLAB command window.
- In the ```BER Tool``` window, set the E<sub>b</sub>/N<sub>0</sub> range to ```-10:10```
- Choose the modulation scheme from the dropdown menu
- Choose the ```Modulation Index``` (See Note 2) and click ```Plot```
- Open the ```Monte Carlo``` tab, set the E<sub>b</sub>/N<sub>0</sub> range to ```-10:10```
- Set the ```Variable name``` to ```ber```
- Choose the model file using the ```Browse``` button and click ```Run```

Note 1: ```Random Generator Set Size``` and ```Modulation Index``` should be set to the same value for each scheme. BPSK/FSk: ```2```, QPSK: ```4```, QAM: ```16``` or ```64```.

Note 2: Scatter plots are produced at a noise level of ```10 dB```.

Note 3: This project was created using MATLAB R2016a. Unless otherwise stated, all values are left to the default setting (e.g. ```Initial Seed``` in the ```AWGN Channel``` block is set to ```67```) 

---
# **Binary Phase-Shift Keying Modulation (BPSK)**
## Explanation
BPSK is a modulation scheme which shifts the phase of the output signal depending on the input. The input is binary and the zeros and ones are represented by two different phase states in the carrier signal. The phase difference is 180 degrees.


## BPSK without Raised Cosine Filter
### Simulink Model Diagram:
![Model](/BPSK/Model.PNG)
### Scatter Plot (Before Noise)
![ScatterPlot(BeforeNoise)](/BPSK/ScatterPlot(BeforeNoise).PNG)
### Scatter Plot (After Noise)
![ScatterPlot(AfterNoise)](/BPSK/ScatterPlot(AfterNoise).PNG)
### BER Performance Plot
![BER-Plot](/BPSK/BER-Plot.PNG)


## BPSK with Raised Cosine Filter
### Simulink Model Diagram:
![Model](/BPSK-RC/Model.PNG)
### Scatter Plot (Before Noise)
![ScatterPlot(BeforeNoise)](/BPSK-RC/ScatterPlot(BeforeNoise).PNG)
### Scatter Plot (After Noise)
![ScatterPlot(AfterNoise)](/BPSK-RC/ScatterPlot(AfterNoise).PNG)
### BER Performance Plot
![BER-Plot](/BPSK-RC/BER-Plot.PNG)
___
# **Quadrature Phase-Shift Keying Modulation (QPSK)**
## Explanation
QPSK (A.K.A. Double Side Band Suppressed Carrier) is a variation of PSK in which two bits are modulated at once, selecting one of four possible carrier phase shifts (0&deg;, 90&deg;, 180&deg;, or 270&deg;). QPSK doubles the bandwidth efficiency leaving more space for other users.


## QPSK without Raised Cosine Filter
### Simulink Model Diagram:
![Model](/QPSK/Model.PNG)
### Scatter Plot (Before Noise)
![ScatterPlot(BeforeNoise)](/QPSK/ScatterPlot(BeforeNoise).PNG)
### Scatter Plot (After Noise)
![ScatterPlot(AfterNoise)](/QPSK/ScatterPlot(AfterNoise).PNG)
### BER Performance Plot
![BER-Plot](/QPSK/BER-Plot.PNG)


## QPSK with Raised Cosine Filter
### Simulink Model Diagram:
![Model](/QPSK-RC/Model.PNG)
### Scatter Plot (Before Noise)
![ScatterPlot(BeforeNoise)](/QPSK-RC/ScatterPlot(BeforeNoise).PNG)
### Scatter Plot (After Noise)
![ScatterPlot(AfterNoise)](/QPSK-RC/ScatterPlot(AfterNoise).PNG)
### BER Performance Plot
![BER-Plot](/QPSK-RC/BER-Plot.PNG)
___
# **Frequency Shift Keying (FSK)**
## Explanation
FSK is a digital modulation scheme in which the frequency of the carrier signal varies according to the digital signal changes. The output of a FSK-modulated wave is high in frequency for a binary High input and is low in frequency for a binary Low input.

## FSK without Raised Cosine Filter
### Simulink Model Diagram:
![Model](/FSK/Model.PNG)
### Scatter Plot (Before Noise)
![ScatterPlot(BeforeNoise)](/FSK/ScatterPlot(BeforeNoise).PNG)
### Scatter Plot (After Noise)
![ScatterPlot(AfterNoise)](/FSK/ScatterPlot(AfterNoise).PNG)
### BER Performance Plot
![BER-Plot](/FSK/BER-Plot.PNG)


## FSK with Raised Cosine Filter
### Simulink Model Diagram:
![Model](/FSK-RC/Model.PNG)
### Scatter Plot (Before Noise)
![ScatterPlot(BeforeNoise)](/FSK-RC/ScatterPlot(BeforeNoise).PNG)
### Scatter Plot (After Noise)
![ScatterPlot(AfterNoise)](/FSK-RC/ScatterPlot(AfterNoise).PNG)
### BER Performance Plot
![BER-Plot](/FSK-RC/BER-Plot.PNG)
___

# **Quadrature Amplitude Modulation (QAM)**
## Explanation
QAM is a scheme used to transmit two digital bit streams or two analog signals by modulating the amplitudes of two carrier waves so that they differ in phase by 90&deg;. The two signals can be mathematically represented by a sine and a cosine wave.

## Extra simulation steps
- Click on the ```QAM Modulator Baseband``` block
- Set the ```M-ary number``` to ```16``` or ```64```
- Set the ```Normalization method``` to ```Average Power```


## QAM-16 without Raised Cosine Filter
### Simulink Model Diagram:
![Model](/QAM16/Model.PNG)
### Scatter Plot (Before Noise)
![ScatterPlot(BeforeNoise)](/QAM16/ScatterPlot(BeforeNoise).PNG)
### Scatter Plot (After Noise)
![ScatterPlot(AfterNoise)](/QAM16/ScatterPlot(AfterNoise).PNG)
### BER Performance Plot
![BER-Plot](/QAM16/BER-Plot.PNG)


## QAM-16 with Raised Cosine Filter
### Simulink Model Diagram:
![Model](/QAM16-RC/Model.PNG)
### Scatter Plot (Before Noise)
![ScatterPlot(BeforeNoise)](/QAM16-RC/ScatterPlot(BeforeNoise).PNG)
### Scatter Plot (After Noise)
![ScatterPlot(AfterNoise)](/QAM16-RC/ScatterPlot(AfterNoise).PNG)
### BER Performance Plot
![BER-Plot](/QAM16-RC/BER-Plot.PNG)


## QAM-64 without Raised Cosine Filter
### Simulink Model Diagram:
![Model](/QAM64/Model.PNG)
### Scatter Plot (Before Noise)
![ScatterPlot(BeforeNoise)](/QAM64/ScatterPlot(BeforeNoise).PNG)
### Scatter Plot (After Noise)
![ScatterPlot(AfterNoise)](/QAM64/ScatterPlot(AfterNoise).PNG)
### BER Performance Plot
![BER-Plot](/QAM64/BER-Plot.PNG)


## QAM-64 with Raised Cosine Filter
### Simulink Model Diagram:
![Model](/QAM64-RC/Model.PNG)
### Scatter Plot (Before Noise)
![ScatterPlot(BeforeNoise)](/QAM64-RC/ScatterPlot(BeforeNoise).PNG)
### Scatter Plot (After Noise)
![ScatterPlot(AfterNoise)](/QAM64-RC/ScatterPlot(AfterNoise).PNG)
### BER Performance Plot
![BER-Plot](/QAM64-RC/BER-Plot.PNG)
