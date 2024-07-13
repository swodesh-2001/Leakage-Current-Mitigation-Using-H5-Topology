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

$$
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
$$

### H4 Bipolar Modes

$$  
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
$$

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

$$
V_{CM} = \frac{V_{AN} + V_{BN}}{2}
$$

In this mode, positive voltage is transferred when:

- $V_{AN} = V_{DC}$
- $V_{BN} = 0$

Therefore,

$$
V_{CM} = \frac{V_{DC}}{2}
$$


#### MODE 2 ( Freewheeling )
![image](https://github.com/user-attachments/assets/edf1255d-be2d-4631-8f2a-b3a2aa29a176)

In this mode
- DC side is decoupled from Freewheeling side.
- Lower diode clamps VBN  to VDC/2
- Magnetic field stored in the inductor collapses through switch S1 and FD D3 
- Applying KVL we obtain  
         $V_{CM} = /frac{V_{DC}}{2}$

#### MODE 3 
![image](https://github.com/user-attachments/assets/b549ef09-61d8-4ce2-8a80-144c1432e505)
![image](https://github.com/user-attachments/assets/447d4b75-3db7-46f3-aaaa-b5b1e801d44e)

In this mode, negative voltage is transferred when:

- $V_{AN} = 0 /text{and}  V_{BN} = V_{DC}$
- $V_{CM} = V_{DC} / 2$

#### MODE 4 ( Freewheeling )
![image](https://github.com/user-attachments/assets/3956a7fe-7c24-4cd7-8d4f-b63619d2c8b2)  
In this instant
- DC side is decoupled from Freewheeling side.
- Upper diode clamps VAN  to VDC/2 
- Magnetic field stored in the inductor collapses through freewheeling diode D1 and switch S3 
- Applying KVL we obtain
     $V_{CM} = /frac{V_{DC}}{2}$

**SO IN ALL MODE CMV IS CONSTANT**  
![image](https://github.com/user-attachments/assets/6249b45c-c95b-4512-88e1-1d8376da5bfc)

$$  
\begin{array}{|c|c|c|c|c|}
\hline
\text{Modes} & V_{AN} & V_{BN} & V_{DM} & V_{CM} \\
\hline
1 & V_{dc} & 0 & V_{dc} & \frac{V_{dc}}{2} \\
\hline
2 & \frac{V_{dc}}{2}  & \frac{V_{dc}}{2}  & 0 & \frac{V_{dc}}{2} \\
\hline
3 & 0 & V_{dc} & -V_{dc} & \frac{V_{dc}}{2} \\
\hline
4 & \frac{V_{dc}}{2}  & \frac{V_{dc}}{2}  & 0 & \frac{V_{dc}}{2} \\
\hline
\end{array}  
$$

---

## Methodology
![image](https://github.com/user-attachments/assets/a0803dde-4257-4e9a-b0f3-b63c0f994194)

- `MPPT` continuously checks PV current and Voltage to adjust them in order to track the point at which they produce maximum power output.

- The function of `DC-DC boost converter` is to regulate and adjust the output voltage of PV panel in order to match the desired voltage to achieve maximum power output. It is done by adjusting duty cycle given from the output of MPPT block.

- To achieve DC-link voltage regulation and grid synchronization, two control loops, `inner grid current control loop` and `outer DC-link voltage control loop` are used.


### Outer DC-link voltage control loop

- This loop is responsible for regulating the DC-link voltage at a constant value. Here, the constant value is taken as 400 V.

- Voltage regulation is achieved by adjusting the reference DC current Id_ref, which is obtained by feeding error signal to a properly tuned PI controller. If the DC-link voltage is less, then less current will be injected to grid and voltage again rises and vice versa.

![image](https://github.com/user-attachments/assets/95ae70a6-246a-495b-90a2-51cf56881c2d)

### Inner grid current control loop

- Clarke Transformation is used to extract alpha and beta component of reference current. Iq is made equal to zero to make reactive power injection zero.

- The alpha component of current obtained is fed to Hysteresis Band Current Controller, which acts as reference current to control the inverter output current.

![image](https://github.com/user-attachments/assets/0dcdcd1a-4ea3-4d74-b85a-3299a19c4aac)

## Simulation

![image](https://github.com/user-attachments/assets/9f3a32d4-de1c-4002-b06b-e18e4661a74c)

### SPWM Methodology ( Hardware Design)
![image](https://github.com/user-attachments/assets/1456324f-9adb-448e-998a-4dd3a89d08a6)

### Microcontroller-1 Flowchart

```mermaid
flowhcart TD
    start((START))
    check[Check Boost Converter<br>Output Voltage (Vout)]
    decision{Vout > Vset}
    increase[Increase Duty Cycle<br>Of PWM]
    decrease[Decrease Duty Cycle<br>Of PWM]

    start --> check
    check --> decision
    decision -- Yes --> decrease
    decision -- No --> increase
    increase --> check
    decrease --> check
```

### Microcontroller-2 Flowchart
![image](https://github.com/user-attachments/assets/6dfd897a-4db5-40b1-9d1e-d86a836bc10d)

## Hardwares Developed

### Zero Crossing Detector

![image](https://github.com/user-attachments/assets/38fff6d8-bfd2-4f7b-8481-e92c3ed38499)


---

### Boost Converter

![image](https://github.com/user-attachments/assets/1492fb52-1d48-489b-bc57-57e50613ba1e)


---

### Current Sensor
![image](https://github.com/user-attachments/assets/f1f078ab-51e1-4731-bc4d-82664194b6ce)


Due to the limitation of commercially available current sensor ACS712, we designed a current sensor on our own using Current Transformer (ZMCT103C) and amplifier circuit.

---

### Inverter Circuit with Driver

![image](https://github.com/user-attachments/assets/197beed5-e06d-4a92-a70a-682391a9cc3a)


---

### Overall Hardware Implementation in Proteus

![image](https://github.com/user-attachments/assets/ce2b655b-0cc3-47b5-9d68-395aa3a1cad8)

Proteus Software is used for simulation. The expected result was obtained after the complete simulation.

---

### Overall Hardware Circuit

![image](https://github.com/user-attachments/assets/7db849df-043c-48c2-9bd1-b88789205010)


---

## Simulation Results And Discussion

The max power the solar panel produces is around 2020 Watt. The reference value for the DC link voltage is set to 400V
![image](https://github.com/user-attachments/assets/02c8094f-0419-4676-bd34-b3ff596a13d9)


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

![image](https://github.com/user-attachments/assets/bfb7b885-63c8-443c-b490-47b3ab876ab1)


---

### Common mode Voltage Comparison

The common mode voltage in H4 unipolar fluctuates from 400 to 0 volts, resulting in large leakage current. If we observe the common mode voltage for the H5 topology, the VCM is almost constant with little spike fluctuation and the steady value sits around 200V.

![image](https://github.com/user-attachments/assets/5c287457-3028-462c-a115-8f4a73f2f2b0)


Due to the reduction in magnitude of CMV and its rate of fluctuation, the leakage current is suppressed.

![image](https://github.com/user-attachments/assets/3b368809-2c5e-43ee-8aca-6432de160f7b)


| **Topology**                    | **Leakage Current (RMS)** |
|---------------------------------|---------------------------|
| H4 with unipolar modulation     | 285 mA                    |
| H5                              | 1.35 mA                   |

 

---

### Proteus Result (With Hysteresis Current Control)

![image](https://github.com/user-attachments/assets/b320d0d8-350d-436c-a108-e1ef1ad93de1)


Some spikes due to switching of inverter. Constant CMV was obtained ensuring zero leakage current. Output inverter current and grid voltage are in phase ensuring unity power factor.

---

### Hardware Result (With SPWM Modulation)

![image](https://github.com/user-attachments/assets/fa9f0455-d114-4407-b9f2-665868d3d72a)

![image](https://github.com/user-attachments/assets/4b4b5b5e-75e0-4764-af62-b02c8832e3e0)

---

## Future Recommendation

- Inject the power to the grid using a larger wattage solar panel and with proper protection circuit.
- IR2110 (Mosfet Driver IC) available in Nepal were of cheap quality, resulting in blowing out. So using mosfet driver imported from a good company is recommended.

---

## References

1. **IEEE Recommended Practice For Utility Interface Of Photovoltaic (PV) Systems, IEEE Std 929-2000 2000.**
2. **VDE012611 “Automatic Disconnection Device Between A Generator And The Public Low Voltage Grid.” 2008.**
3. **M. Calais, V. G. Agelidis, and M. Meinhardt, “Multilevel Converters For Single-phase Grid Connected Photovoltaic Systems: An Overview,” Solar Energy, vol. 66, no. 5, pp. 325–335, 1999.**
4. **M. Victor, F. Greizer, S. Bremicker, and U. Hubler, “Method of Converting a Direct Current Voltage from a Source of Direct Current Voltage, More Specifically From A Photovoltaic Source Of Direct Current Voltage, Into an Alternating Current Voltage,” U.S. Patent 7411802, Aug. 12, 2008.**
5. **Frede Blaabjerg, Remus Teodorescu, Marco Liserre, Adrian V. Timbus “Overview of Control and Grid Synchronization for Distributed Power Generation Systems”, IEEE Transactions on Industrial Electronics, Vol. 53, No. 5, October 2006.**

## ANNEXES

### Mosfet Driver Circuit (Version 1)
Version 1 represents circuit design in matrix board with external wiring
![image](https://github.com/user-attachments/assets/d926d720-b97f-497e-be62-98264204ee35)  
Due to some problems with bootstrap capacitor, we switched to version 2 

### Mosfet Driver Circuit (Version 2)
Version 2 represents single layer PCB design of  circuit involving external wiring 
![image](https://github.com/user-attachments/assets/2069cdd6-ed79-4d94-8be6-01d7cc7dccfe)  
Still this version has problems related to common ground due to wiring problems

### Double Layered PCB Design V3
![image](https://github.com/user-attachments/assets/dfc19983-5ee2-4fcf-a425-9bda3ba0fe6a)

FeCL3 was used for etching the PCB. 

![image](https://github.com/user-attachments/assets/4ad65fc8-130c-41bd-a8c0-6057df75e817)


### Whole Hardware in Nutshell   
![image](https://github.com/user-attachments/assets/c3de7c14-0020-4d62-a4e8-26a1a27f1aa4)

![image](https://github.com/user-attachments/assets/04c04a63-0f58-442c-abf1-ef8559820bb5)


