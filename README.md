<div align="center">
  
# DEVELOPMENT OF NEW CONTROL STRATEGY IN TRANSFORMER-LESS GRID CONNECTED PV INVERTER TO REDUCE LEAKAGE CURRENT

**Presented by:**
 **Rachana Subedi** (076BEL033)  
 **Shashwot Shrestha** (076BEL043)  
 **Sushil Phuyal** (076BEL047)  
 **Swodesh Sharma** (076BEL048)  

**Project Supervisor:**
**Prof. Dr. Indraman Tamrakar**

**Tribhuwan University**  
**Institute of Engineering**  
**Pulchowk Campus**  

**Department of Electrical Engineering**  
**Lalitpur, Nepal**  

**Final Presentation on Final Year Project-II**  
**March 2024**

</div>

---

## Table of Contents

1. [Introduction](#introduction)
2. [Literature Review](#literature-review)
3. [Problem Statement](#problem-statement)
4. [Objectives](#objectives)
5. [Scope and Limitation](#scope-and-limitation)
6. [H5 Solution](#h5-solution)
7. [Methodology](#methodology)
8. [System Under Consideration](#system-under-consideration)
9. [Results and Discussion](#results-and-discussion)
10. [Future Recommendations](#future-recommendations)
11. [References](#references)

---

## Introduction

According to IEEE Standard [1], any PV panels must be grounded properly. The grounding induces parasitic earth capacitances (ranges from 6nF to 5μF).

![image](https://github.com/user-attachments/assets/e41d4165-0cea-427b-944f-d863847006f0)


This leakage capacitance becomes allows the path for the flow of leakage current into the inverter and to the grid.

- This capacitance will be the part of `LC Resonant Circuit` and constitutes for flow of leakage current. According to the `German standard VDE0126-1-1`, leakage currents greater than 300 mA must trigger a break within 0.3s and send a fault signal [2].

![image](https://github.com/user-attachments/assets/8da91c17-a5a2-4d92-bdd1-618bf750fc13)

![image](https://github.com/user-attachments/assets/92b6f37c-b464-4e1d-9b93-eda0d751561a)

- According to the simplified circuit reduction, the leakage current depends upon the common-mode (CM) voltage.

- Thus, the leakage current depends upon the magnitude and nature of CM voltage.

- If $V_{CM}$   is constant i.e., DC. Then, it’s frequency is zero. So, the denominator quantity becomes infinity. Thus, leakage current reduces to zero.


---

## Literature Review

- The ground capacitance developed between the PV array and the earth has been affected by the potential difference, also known as common-mode (CM) voltage of the inverter MOSFETs. 

- As a consequence, the magnitude and nature of the common mode voltage leads to the injection of ground capacitive current or leakage current to the inverter and to the grid too [3]. 

- If the common mode voltage is kept constant i.e., DC, the leakage current essentially reduces to zero. Since, for a conventional H4 bridge inverter, CM voltage cannot be constant. So, using H4 topology for leakage reduction with proper efficiency is not possible.
  
- An effective method of weakening the CM voltage is by decoupling the AC side from the DC side during the freewheeling period. Several inverter topologies like H5 [4] which has DC side decoupling, H6 [5], and HERIC [6] which has AC side decoupling, are being developed for reducing the CMV.

- Similarly, to further clamp the common mode voltage to a certain fixed value, circuits are proposed to clamp the CM voltage to some certain value during the freewheeling period[7], [8]. 

---

## Problem Statement

- The common-mode (CM) currents(leakage current) of the transformer-less PV inverters could flow through the parasitic capacitor between the PV array and the ground.

- The leakage current will lead to serious electromagnetic interference and insecurity, and reduce the reliability of the PV inverter systems in practice,


- **Unipolar Modulation**  
  ![image](https://github.com/user-attachments/assets/a9024455-580d-47de-be9e-c9fb65776628)

- **Bipolar Modulation**  
![image](https://github.com/user-attachments/assets/21b6b6d5-c755-4b72-9c48-5e76d9fc1f59)

### Problem with H4 Bridge Topology
![image](https://github.com/user-attachments/assets/c17e110c-1d2d-42ea-9465-5a775e6c719a)

### H4 Unipolar Modes

```math
\begin{array}{|c|c|c|c|c|}
\hline
\text{Modes} & V_{AN} & V_{BN} & V_{DM} & V_{CM} \\
\hline
1 & V_{dc} & 0 & V_{dc} & \frac{V_{dc}}{2} \\
\hline
2 & V_{dc} & V_{dc} & 0 & V_{dc} \\
\hline
3 & 0 & V_{dc} & -V_{dc} & \frac{V_{dc}}{2} \\
\hline
4 & 0 & 0 & 0 & 0 \\
\hline
\end{array}
```

### H4 Bipolar Modes

```math
\begin{array}{|c|c|c|c|c|}
\hline
\text{Modes} & V_{AN} & V_{BN} & V_{DM} & V_{CM} \\
\hline
1 & V_{dc} & 0 & V_{dc} & \frac{V_{dc}}{2} \\
\hline
2 & 0 & V_{dc} & -V_{dc} & \frac{V_{dc}}{2} \\
\hline
3 & 0 & V_{dc} & -V_{dc} & \frac{V_{dc}}{2} \\
\hline
4 & V_{dc} & 0 & V_{dc} & \frac{V_{dc}}{2} \\
\hline
\end{array}
```

---

## Objectives

- To develop an inverter topology with an optimized number of switches and modulation techniques (combination of unipolar and bipolar) to reduce the leakage current.
- To replicate the hardware setup for H5 topology inverter.

---

## Scope and Limitations

A new efficient topology (H5) has been derived that has minimum conduction losses, incorporates both unipolar and bipolar modulation, low LC, and few high-speed switches.

The unreliability of hardware components available in our country was a great obstacle to obtaining the expected result.

---

## H5 Solution

- The proposed H5 inverter consists of an additional S5 switch inserted at the positive DC bus which is called DC decoupling type TLI. 
- The turning off of this switch S5 is responsible for decoupling the DC side or PV side from the grid.

![Proposed H5 inverter topology](https://github.com/user-attachments/assets/89e7ca64-0379-4345-b1ff-c3e5145362e8)

#### MODE 1
![image](https://github.com/user-attachments/assets/375309a2-c718-42e5-b6d8-42470771dbaf)
![image](https://github.com/user-attachments/assets/7950771e-6d42-43b8-9698-b7be37e67ac0)

$$ V_{CM} = \frac{V_{AN} + V_{BN}}{2} $$
In this mode, positive voltage is transferred    
$ V_{AN} = V_{DC} $ and $ V_{BN} = 0 $    
$ V_{CM} = \frac{V_{DC}}{2} $

---

## Methodology

### Simulation

![Methodology of the proposed system in Matlab](./images/image4.png)

**MPPT** continuously checks PV current and voltage to adjust them in order to track the point at which they produce maximum power output.

The function of the **DC-DC boost converter** is to regulate and adjust the output voltage of the PV panel in order to match the desired voltage to achieve maximum power output. It is done by adjusting the duty cycle given from the output of the MPPT block.

To achieve **DC-link voltage regulation and grid synchronization**, two control loops, the inner grid current control loop, and the outer DC-link voltage control loop are used.

---

### Outer DC-link voltage control loop

This loop is responsible for regulating the DC-link voltage at a constant value. Here the constant value is taken as 400 V.

Voltage regulation is achieved by adjusting the reference DC current **Id_ref**, which is obtained by feeding the error signal to a properly tuned **PI controller**. If the DC-link voltage is less, then less current will be injected into the grid and the voltage again rises and vice versa.

**Clarke Transformation** is used to extract the alpha and beta component of reference current. Iq is made equal to zero to make reactive power injection zero.

The alpha component of current obtained is fed to the **Hysteresis Band Current Controller**, which acts as a reference current to control the inverter output current.

![DC link voltage control](./images/image5.png)  
![Clarke transformation](./images/image6.png)

---

### Hysteresis Band Current Control

It is an instantaneous feedback current control method. Actual current and reference current are compared here. If the actual current magnitude hits the upper band, it is made to return back by decreasing its magnitude and if the actual current hits the lower band, it is made to return back by increasing its magnitude.

![Hysteresis band current control for gate signal generation](./images/image7.png)

---

### Single Phase Locked Loop (PLL)

**Single Phase Locked Loop (PLL)** is used for extracting the frequency and phase angle (wt_grid) of the grid voltage.

![Single phase PLL for wt_grid extraction](./images/image8.png)

---

### System Under Consideration (Simulation)

![Complete MATLAB Simulink model](./images/image9.png)

---

### SPWM Methodology (Hardware Design)

![Methodology of the Hardware system](./images/image10.png)

---

### Microcontroller-1 Flowchart

![Flowchart of Microcontroller 1 for generating duty signals to Boost Converter](./images/image11.png)

---

### Microcontroller-2 Flowchart

![Flowchart of Microcontroller 2 for generating gate signals](./images/image12.png)

---

### Zero Crossing Detector

![Zero Crossing Detector (ZCD)](./images/image13.png)

---

### Boost Converter

![Boost Converter and its output](./images/image14.png)

---

### Current Sensor

![Current Sensor and its working](./images/image15.png)

Due to the limitation of commercially available current sensor ACS712, we designed a current sensor on our own using Current Transformer (ZMCT103C) and amplifier circuit.

---

### Inverter Circuit with Driver

![Inverter Circuit and its output voltage in oscilloscope](./images/image16.png)

---

### Overall Hardware Implementation in Proteus

![Complete circuit in proteus and its output](./images/image17.png)

Proteus Software is used for simulation. The expected result was obtained after the complete simulation.

---

### Overall Hardware Circuit

![Final hardware design of the whole system](./images/image18.png)

---

## Simulation Results And Discussion

The max power the solar panel produces is around 2020 Watt. The reference value for the DC link voltage is set to 400V

![Power delivered from proposed H5 inverter](./images/image19.png)  
![DC link voltage](./images/image20.png)

---

### Electrical parameters fed into the grid

| **Parameter**                       | **Value**      |
|-------------------------------------|----------------|
| Power out from PV panel             | 2020 Watt      |
| PV panel current                    | 8.438 A        |
| PV panel voltage                    | 243.1 V        |
| Active power injected to grid       | 1890 Watt      |
| Reactive power injected to grid     | -30 VA         |
| Current injected to grid            | 8.558 A (RMS)  |
| Efficiency                          | 93.56          |

![Injected grid current using HBCC](./images/image21.png)

---

### Common mode Voltage Comparison

The common mode voltage in H4 unipolar fluctuates from 400 to 0 volts, resulting in large leakage current. If we observe the common mode voltage for the H5 topology, the VCM is almost constant with little spike fluctuation and the steady value sits around 200V.

![Magnified CM voltage in H4](./images/image22.png)  
![Magnified CM voltage in proposed H5](./images/image23.png)

Due to the reduction in magnitude of CMV and its rate of fluctuation, the leakage current is suppressed.

| **Topology**                    | **Leakage Current (RMS)** |
|---------------------------------|---------------------------|
| H4 with unipolar modulation     | 285 mA                    |
| H5                              | 1.35 mA                   |

![Leakage current in standard H4 bridge](./images/image24.png)  
![Leakage current in proposed H5 inverter](./images/image25.png)

---

### Proteus Result (With Hysteresis Current Control)

![Waveform of CMV](./images/image26.png)  
![Waveform of Output Current](./images/image27.png)

Some spikes due to switching of inverter. Constant CMV was obtained ensuring zero leakage current. Output inverter current and grid voltage are in phase ensuring unity power factor.

---

### Hardware Result (With SPWM Modulation)

![Various output waveforms of the inverter](./images/image28.png)

---

## Future Recommendation

- Inject the power to the grid using a larger wattage solar

 panel and with proper protection circuit.
- IR2110 (Mosfet Driver IC) available in Nepal were of cheap quality, resulting in blowing out. So using mosfet driver imported from a good company is recommended.

---

## References

1. **IEEE Recommended Practice For Utility Interface Of Photovoltaic (PV) Systems, IEEE Std 929-2000 2000.**
2. **VDE012611 “Automatic Disconnection Device Between A Generator And The Public Low Voltage Grid.” 2008.**
3. **M. Calais, V. G. Agelidis, and M. Meinhardt, “Multilevel Converters For Single-phase Grid Connected Photovoltaic Systems: An Overview,” Solar Energy, vol. 66, no. 5, pp. 325–335, 1999.**
4. **M. Victor, F. Greizer, S. Bremicker, and U. Hubler, “Method of Converting a Direct Current Voltage from a Source of Direct Current Voltage, More Specifically From A Photovoltaic Source Of Direct Current Voltage, Into an Alternating Current Voltage,” U.S. Patent 7411802, Aug. 12, 2008.**
5. **Frede Blaabjerg, Remus Teodorescu, Marco Liserre, Adrian V. Timbus “Overview of Control and Grid Synchronization for Distributed Power Generation Systems”, IEEE Transactions on Industrial Electronics, Vol. 53, No. 5, October 2006.**



