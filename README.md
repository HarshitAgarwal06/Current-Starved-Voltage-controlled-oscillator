
# Table of Content

* [Abstract](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#abstract)
* [Reference Circuit Details](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#reference-circuit-details)
* [Calculation of Propogation Delay](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#calculation-of-propogation-delay)
* [Tool Used](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#tool-used)
* [Schematic](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#schematic)
* [Symbol](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#symbol)
* [Final Schematic](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#final-schematic)
* [Simulation Result](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#simulation-result)
* [Transistor Count](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#transistors-count)
* [Netlist](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#netlist)
* [Author](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#author)
* [Acknowledgement](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#acknowledgement)
* [Reference](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/new/main?readme=1#reference)

# Abstract
This paper proposes a design of voltage controlled Current starved ring oscillator based on 28nm node technology. Oscillator is an electronic device which has a very basic functioning of generating clock in any microprocessor. Oscillators are also used in communication field for carrier synthesis. Now a days oscillators are also seeing application in True random number generator circuits due to the random nature of jitter which oscillators have. Many configurations & topologies are present for the designing of oscillator but in this paper, we have chosen Current Starved design due to its nature of low power.  

# Reference Circuit Details
Oscillator is a circuit which produces a continuous, repeated, alternating waveform without any input. Oscillator’s have multiple application in VLSI & Communication field, some of the basic application of oscillator is to provide clock to microprocessor. Traditionally oscillator has been designed using CMOS methods but these oscillators suffered from high power dissipation problem. To resolve this issue Current starved VCO has been implemented in this paper. VCO can be build using many techniques [1]. 

![image](https://user-images.githubusercontent.com/100519126/155892440-4565385b-0277-467d-add6-cc505663e6a0.png)

Fig. 1a shows a standard push-pull type CMOS based inverter where as Fig 1b shows a current starved inverter. In current starved inverter drain current is controlled by the gate potential of the M3 & M0 MOSFETs. This property of the circuit makes it a voltage-controlled device. As the value of the voltage increases, drain current increases which leads to reduction in time of charging or discharging the load. 

The VCO shown in the Fig 2 have five stages where each stage has one current starved inverter which are designed in such a way that the output of one stage drives the input of next stage and the output of last stage is connected with the input of the first stage. Apart from these 5 stages, buffers can also be used to minimize the affect of large capacitor load. A cascade connection of five stages leads to considerable amount of slack between the stage output of VCO. 

When an ideal pulse is applied at the input of VCO as an initial condition, the output of the stage drives from high potential to low potential as N-MOS is in on condition. As the output voltage moves from high potential to low potential N-MOS M1 (refer Fig 1b) drives from saturation region to triode region. Due to the current starved inverter, the current starts to fall & M0 is switched to deep triode region, this results in saving of power which was missing in CMOS based inverter

![image](https://user-images.githubusercontent.com/100519126/155892916-7cd53e13-3438-447c-847e-baf7fa72cfa8.png)

# CALCULATION OF PROPOGATION DELAY
Propagation delay is the time take by the circuit to fall from 90% to 10% or rise from 10% to 90% of the output voltage. For the current starved inverter propagation delay calculation, we have taken reference of [2] and found out that the fall & rise time would be as shown in Fig 3.

![image](https://user-images.githubusercontent.com/100519126/155892931-afafca50-337a-4f5a-9fb2-562916f07e48.png)

# Tool Used
**Synopsys Custom Compiler:**  The Synopsys Custom Compiler™ design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. This tool was used to design the circuit on a transistor level.

![image](https://user-images.githubusercontent.com/100519126/155893129-13e0228d-e9c7-46a5-bdad-a81436e0b4ac.png)

**Synopsys Primewave:**  PrimeWave™ Design Environment is a comprehensive and flexible environment for simulation setup and analysis of analog, RF, mixed-signal design, custom-digital and memory designs within the Synopsys Custom Design Platform. This tool helped in various types of simulations of the above designed circuit.
**Synopsys 28nm PDK:**  The Synopsys 28nm Process Design Kit(PDK) was used in creation and simulation of the above circuit design.

# Schematic
Current Starved VCO
![image](https://user-images.githubusercontent.com/100519126/155893244-911b6cfe-2d6a-474a-8053-a2b470728f08.png)

# Symbol
Current Starved VCO
![image](https://user-images.githubusercontent.com/100519126/155893287-797adbf8-71fe-43e0-9f93-af9eb6fbbc13.png)

# Final Schematic
![image](https://user-images.githubusercontent.com/100519126/155893368-f5c6077e-3bef-4b0f-9cab-3840fd516001.png)

# Simulation Result
Current Starved VCO frequency depends upon the "Vctrl" value, as the value of "Vctrl" increases the value of driving current increases hence the final frequency also increases. 

Below i have simulated the VCO with a "Vctrl" value of **0.8v**

At the give voltage circuit has given a freq of **10.9Ghz**
![image](https://user-images.githubusercontent.com/100519126/155895069-ed6f5da3-4dc4-4426-9026-f99273905cff.png)

Below image was produced after sweeping "Vctrl" for 4 different values:- 

**Red:-** 0.1V

**Blue:-** 0.466V

**Yellow:-** 0.833V

**Green:-** 1.2V

![image](https://user-images.githubusercontent.com/100519126/155893967-db8955d6-0f8b-4393-9886-3c27ebde5b99.png)

We can clearly define from the above image that how increasing the value of "Vctrl" defines the frequency of the oscillator.

# Transistors Count
Nmos:- 11

Pmos:- 11

Total:- 22

# Netlist

To see the netlist click [here](https://github.com/HarshitAgarwal06/Current-Starved-Voltage-controlled-oscillator/blob/main/CSVCO_netlist.txt)

# Author
Harshit Agarwal, Mtech in Microelectronics at  Indian Institute Of Information Technology Road Devghat, Jhalwa, Prayagraj, Uttar Pradesh 211015

# Acknowledgement
[Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.](https://in.linkedin.com/in/kunal-ghosh-vlsisystemdesign-com-28084836)

[Cloud Based Analog IC Design Hackathon](https://hackathoniith.in/)

[Synopsys India](https://www.synopsys.com/)

# Reference 
[1]	M.  Jamal  Deen,  “Ultra  Low-Voltage  Low-Power  Voltage  Controlled  Oscillator”,  Electrical  and  Computer  Engineering  Department,  CRL  226  McMaster  University,  Hamilton,  ON,  Canada  L8S  4K1. 

[2]	Manish Goswami “0.4mW, 0.27pJ/bit true random number generator using jitter, metastability and current starved topology”, Electronics & communication, Indian Institue of Information technology, Allahabad.

[3] BP Panda “Design  of  a  Novel  Current  Starved  VCO  via Constrained  Geometric  Programming”, Department  of  Electronics  and  Communication  Engineering,   National  Institute  of  Technology,  PPRourkela,  Orissa,  India School  of  Electrical  Engineering

