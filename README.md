# Intel_CKT_Training

## Table of contents
+ **[ Day 1 - Fundamental of VLSI Design & Overview of Sand-to-Silicon ](https://github.com/xinniteo/Intel_CKT_Training#day-1)**
  <details><summary> Theory </summary>  
  
  [Theory - Fundamental of VLSI Design & Overview of Sand-to-Silicon](https://github.com/xinniteo/Intel_CKT_Training/blob/main/README.md#theory---fundamental-of-vlsi-design-&-overview-of-sand---to---silicon)
  </details>
  <details><summary> Prerequisite Assignments (TBD by 15/1) </summary>  
 
 <!---
  * RC-Circuit-Assignment (TBD)
  * Electrical-Circuits-Assignment (TBD)
  * Digital-Circuits-Assignment (TBD)
  * Semiconductor-Devices-Assignment (TBD)
-->
  </details>

+ **[ Day 2 - IC Manufacturing Process ](https://github.com/xinniteo/Intel_CKT_Training#day-2)**
  <details><summary> Theory </summary>  
  
  [Theory - Analog VLSI Design Flow & CMOS Fabrication Process](https://github.com/xinniteo/Intel_CKT_Training#theory---analog-vlsi-design-flow--cmos-fabrication-process)
  </details>
  <details><summary> Assignment </summary>  

  [Assignment - Fabrication Process and Layout](https://github.com/xinniteo/Intel_CKT_Training#assignment---fabrication-process-and-layout)
  </details>
 
 
----------------------------------------------------------------
## Day 1
## Theory - Fundamental of VLSI Design & Overview of Sand-to-Silicon
<details><summary> Chip-to-wafer </summary>

### **Chip-to-wafer**
#### Packaged Chip
* Die is the central part of chip
* Package is to connect the silicon die of the IC to the circuit board
* Evolution and different types of Packaged Chip, example:  
![00](https://user-images.githubusercontent.com/121996016/211218848-2589ce0a-61c6-4ebd-b7cd-7b9c6188c8c0.jpg)

  * SIP (System In Package): 
    * Integrated circuits enclosed in one or more chip carrier packages that may be stacked using package on package where a single independent function can be achieved by placing or laminating multiple chips in a single package
    * ![01](https://user-images.githubusercontent.com/121996016/211218763-cce783af-33d3-40bf-ad4e-5ebf28678cb8.png)

  * DIP (Dual In-line Package): 
    * an electronic component package with a rectangular housing and two parallel rows of electrical connecting pins
    * ![02](https://user-images.githubusercontent.com/121996016/211218866-533bb58a-6f84-428f-a6c9-1ab7cb522f8c.jpg)

  * QFN (Quad Flat No-lead package): 
    * a lead frame-based package which using surface-mount technology that comes in small size and offers moderate heat dissipation in PCBs 
    * able to contact and see lead even after assembly
    * ![03](https://user-images.githubusercontent.com/121996016/211218882-c8c685ee-d386-43d8-b8f0-0bdab07d91c5.jpg)

  * BGA ( Ball Gate Array):
    * a type of surface-mount packaging (a chip carrier) used for integrated circuits and permanently mount devices such as microprocessors 
    * able to provide more interconnection pins than can be put on a dual in-line or flat package
    * ![04](https://user-images.githubusercontent.com/121996016/211218901-8f07ae64-801f-49c2-ad1b-ecc0a2f56317.png)

#### Die and Wafer
* generally die size is (1x1)mm or (1x2)mm
* wafer diameter is around 12 inch ~ 300 mm
* a single wafer contains 10’s of thousands die  

   </details>
  
<details><summary> Overview of Inside the Die </summary>

### **Overview of Inside the Die**
![05](https://user-images.githubusercontent.com/121996016/211218924-a502ad35-b6fd-48c1-9249-28adcab0167b.png)
* Analog and RF
  * Made by custom VLSI flow
  * Clock, voltage reference and regulator, amplifiers and filters, ADC and DAC interfaces, and etc.
* Digital
  * made by standard cells using semicustom VLSI design flow
  * Gates, multiplexers, decoders, counters, registers, FSM and etc.
* Memory and Memory Controller
  * Static Random Access Memory (SRAM) and SRAM controller

   </details>
  
<details><summary> Moore’s Law </summary>

### **Moore’s Law**
  
* Moore’s Law defines the number of transistors in a dense integrated circuit doubles every 2 years
  * Every two years, the feature size is reduced by 1/sqrt(2) times

   </details>

<details><summary> VLSI Design Methodology </summary>

### **VLSI Design Methodology**
#### Despite of different design style, proper functionality, low cost and timely execution is much more important
#### Two types of VLSI Design Styles:
1. Field programming gate array (FPGA)
* faster prototyping and cost-effective, basically use in prototyping and testing
* typically consists of input/output buffers, array of configurable logic blocks (CLBs) and programmable interconnect
* structures programming of interconnects is accomplished by programming of RAM
* signal routing between the CLBs and the I/O blocks made by configurable switching matrices
2. Application-specific integrated circuit (ASIC)   
  a.	Standard cell based design  
    * one of the most prevalent full-custom design styles and requires development of a full-custom mask set
    * all commonly used logic cells are developed, characterized, and stored in a standard-cell library  
    * Each cell is characterized according to several different categories, including:  
      * Delay time vs load capacitance and input transition  
      * Circuit simulation model, Timing simulation model, Fault simulation model  
      * Cell data for place-and route  
      * Mask data  

    b.	Full custom design  
      * entire mask design is done without using any library  
      * productivity is very low since geometry, orientation, and placement of every transistor is design individually
      * Developmental cost is huge  
      * full-custom design is rarely used in digital CMOS VLSI due to high labour cost   
      * most rigorous full-custom design can be the design of a memory cell, be it static or dynamic  
      * All the analog and RF designs are full custom design   
  
| FPGA | ASIC |  
| --- | --- |  
| Faster time to market since no layout, masks and manufacturing steps needed | Need longer design times to take care of all manufacturing steps |  
| Field programmability as design changes can be absorbed even in field and FPGA reprogrammed | Once manufactured, need to spin again a new chips in case of bugs |
| More power consumption and less performance due to programmable design and low clock speed | Custom design for an application helps in designing for power/performance efficiencies |
| Good for prototyping and low volume designs, as cost would be less | For larger volume of production, cost per unit is much less |
| Generally not possible to have AMS designs | Can support AMS designs |  
  
   </details>
  
<details><summary> VLSI Design Quality </summary>

### **VLSI Design Quality**
#### Importamt criteria to measure the design quality:
1. Testability  
  * Generation of good test vector
  * Availability of good test fixture at speed
  * Design of testable chip
2. Yield and Manufacturability
  * Yield = No. of tested ok chips/ Total no. of Chips
  * Functional Yield = Checks at lower speed
  * Parametric Yield = Checks at required speed
3. Reliability
  * ESD and EOS
  * Electromigration
  * Oxide breakdown
  * Power and ground bouncing
  * On-chip noise and cross-talk
4. Technology Upgradability
  * functional module for design reuse can be achieved quickly with minimal cost
  * able to develop and use advanced CAD tools that automatically generates the physical layout
  
   </details>
  
<details><summary> Package Technology </summary>

### **Package Technology**
* VLSI chips can fail if various packaging constraints and parasitic are not included in the design phase 
* number of ground planes, power planes and the bonding pads greatly affect the behaviours of on-chip power and ground buses
* length of bonding wire and lead length of the package can create serious issue  
* chip designers should work closely with package designers from the start of the project
* Packages are classified by method used to solder the package on the PCB :
  * Pin-through-hole (PTH): holes drilled in PCB, not cost effective but soldering process in not inexpensive
  * Surface Mount Technology (SMT): Directly soldered on the PCB, cost and space effective but expensive equipment's are needed for soldering
  * Plastic: Dominant for many years but it has the disadvantage of being permeable to environmental moisture
  * Ceramic: Power consumption, performance and environmental requirements
* Today’s high pin count, high-frequency operation, heat dissipation and multi-chip packaging requirements are driving the evolution of packaging technologies  

     </details>
  
<details><summary> CAD Tools </summary>

### **CAD Tools**
* essential for timely development of integrated circuits
* CAD technology for VLSI chip design can be categorized into the following areas:
    * High-level synthesis
    * Logic synthesis
    * Circuit optimization
    * Layout
    * Placement and routing
    * Simulation
    * Design rules and checking
  
     </details>
  
 ## Prerequisite Assignments
<!---
<details><summary> RC Circuit Assignment (TBD) </summary> 

### **RC Circuit Assignment**
</details>
<details><summary> Electrical Circuits Asignment (TBD) </summary> 

### **Electrical Circuits Asignment**
</details>
<details><summary> Digital Circuits Assignment (TBD) </summary> 

### **Digital Circuits Assignment**
</details>
<details><summary> Semiconductor Devices Assignment (TBD) </summary> 

### **Semiconductor Devices Assignment**
</details>
-->
----------------------------------------------------------------
## Day 2
## Theory - Analog VLSI Design Flow & CMOS Fabrication Process
<details><summary> Analog VLSI Design Flow </summary>

### **Analog VLSI Design Flow**
#### Analog IC Design Process:
 ![image](https://user-images.githubusercontent.com/121993909/211451557-032a642c-2d99-4425-823c-051fa9349c8f.png)
  
#### Relation of Analog IC Design Process with CAD & PDK:
 ![image](https://user-images.githubusercontent.com/121996016/211657025-5d890a66-a6b4-40da-b249-4b2440879fad.png)

* Electrical Design
  * requires active and passive deice electrical models for:
    * creating, verifying and determining the robustness of design

* Physical Design
  * the process of representing the electrical design in a layout
  * requirements:
    * entering various geometries
    * follow Design Rule Checks (DRC)
    * check Layout Versus Schematic (LVS)
    * extract Parasitic
  
* Test Design
  * process of coordinating, planning, and implementing the measurement of analog and integrated circuit performance
  * Type of tests:
    * functional
    * parametric
    * static
    * dynamic
</details>
</details>

<details><summary> Fabrication of CMOS </summary>

<details><summary> CMOS Fabrication Process </summary>

### **CMOS Fabrication Process**
#### Why CMOS Technology?
* from an analog viewpoint, almost every comparison favours BJT except switch implementation
* however a similar comparison made from digital viewpoint would come up on the side of CMOS
  * due to large volume mixed-mode technology are driven by digital demands

#### CMOS Fabrication Process in 10 Steps:
1. Wafer formation (sand-to-silicon)
* wafers are cut from boules, cylindrical ingots of single crystal silicon which pulled from a crucible of pure molten silicon
* a controlled amounts of impurities are added to the melt to provide the crystal with required electrical properties
* a seed crystal is dipped into the melt to initiate crystal growth
  * the seed is gradually withdrawn vertically from the melt while simultaneously being rotated
* molten silicon attaches itself to the seed and recrystallizes as it is withdrawn
* diameter of ingot is determined by the seed withdrawal and rotation rates

2. Photolithography
* a process of archiving the pattern on a wafer by defining the interests area through photoresists
* wafer is coated with photoresist and subjected to selective illumination through the photomask 
  * photomask is constructed with chromium (chrome) covered quartz glass
  * photoresist is exposed with UV light source
* a developer solvent is used to edge the soluble unexposed photoresist

3. Well and Channel Formation
* 4 CMOS technology processes:
![image](https://user-images.githubusercontent.com/121996016/211666493-08bfc38f-61cc-41fc-a16e-693fd4b7f8dd.png)
* N-well process: to optimize the nMOS transistor performance
* P-well process: to optimize the pMOS transistor performance
* Twin-well process: to allow the optimization of each transistor type
* Triple-well process:
  * to provide good isolation between analog and digital blocks in mixed-signal chips
  * to isolate high-density dynamic memory from logic

4. Silicon Dioxide (SiO2) Deposition
* is achieved by heating silicon wafers in an oxidizing atmosphere
* some common approaches:
  * Wet Oxidation: when oxidizing atmosphere contains water vapor at around 900C to 100C
  * Dry Oxidation: when oxidizing atmosphere is pure oxygen at 1200C
    * forms a better quality oxide than wet oxidation
      * used to form thin, highly controlled gate oxides ; wet oxidation may be used to form thick field oxides

5. Isolation
* to avoid unexpected interactions in individual devices in a CMOS process
* transistor gate consists of a thin gate oxide layer ; thick oxide form through Local Oxidation of Silicon (LOCOS)
* problem: LOCOS-based processes extended some distance laterally during transition between thick and thin oxide
* solution: introduce shallow trench isolation (STI) at >0.35um node
  * STI forms insulating trenches of SiO2 surrounding the transistors (except at active area)


6. Gate Oxide Creation
* commonly in the form of silicon dioxide (SiO2)
* a thin gate oxide layer exists in transistor gate 

7. Gate and Source/Drain Formations
* gate oxide is grow wherever transistors are required (area = source + drain + gate) 
  * elsewhere will be thick oxide or trench isolation
* polysilicon is deposited on chip
* pattern polysilicon (both gates and interconnect)
* etch exposed gate oxide:
  * area of gate oxide where transistors was not covered by polysilicon
    * the chip has windows down to the well or substrate wherever a source/drain diffusion is required
* implant pMOS and nMOS source/drain regions

8. Contacts and Metallization
* contact cuts are made to source, drain, and gate based on the contact mask
  * these are holes etched in the dielectric after the source/drain formation

9. Passivation
* add a protective glass layer called passivation or over glass to prevent the ingress of contaminants 
* overglass cuts is the openings in the passivation layer to allow connection to I/O pads and testprobe points if needed

10. Metrology
*  is the science of measuring
  * everything that built in a semiconductor process need to be measured and feedback to the manufacturing process

</details>

<details><summary> Fabrication of CMOS Using n-well Process Method </summary>  

* Si substrate (p-type)  
![fig1](https://1.bp.blogspot.com/-pHKjBfNkIgc/Xn4Za5zSndI/AAAAAAAAAk4/Hzz77hPgFhwtCFgaIKnArnztuHbcwmlmQCLcBGAsYHQ/s400/fig1.png)

* Oxidation  
![fig3](https://1.bp.blogspot.com/-dCCdjSDPAg4/Xn4Za7YIukI/AAAAAAAAAlY/ZgckoupnLQcsXqThUQ4xDgFiYrZgEgCwQCPcBGAYYCw/s400/fig3.png)

* Photoresist  
![fig4](https://1.bp.blogspot.com/-DaWvC9qYJ4M/Xn4ZbDzzmyI/AAAAAAAAAlc/PjwrfaW2Tikusm1xfDYuXP4m65g1nokqQCPcBGAYYCw/s400/fig4.png)

* Masking  
![fig5](https://1.bp.blogspot.com/-XUF012FnnEM/Xn4ZblTPQfI/AAAAAAAAAlY/H3FrZyo6BRsfpu0IdfLvGJDHyO1QH30jACPcBGAYYCw/s1600/fig5.png)

* Photoresist removal  
![fig6](https://1.bp.blogspot.com/-jbOXyqRh_Tg/Xn4ZcO8J5tI/AAAAAAAAAlg/cc_LYh-6J7g6kxzwAStPRvwShs3TNuJRQCPcBGAYYCw/s400/fig6.png)

*  Etching SiO2  
![fig7](https://1.bp.blogspot.com/-nNAFYJY2wKg/Xn4Zcjms_2I/AAAAAAAAAlc/TY0S4Kb_ImEHjhl6_Y84psi3hsnzg64vwCPcBGAYYCw/s400/fig7.png)

*  Ion implanation: Implant Phosphorus(P) n-type impurity to create N well  
![fig8](https://1.bp.blogspot.com/-E7H2LqI9ssk/Xn4ZYTcbDVI/AAAAAAAAAlc/737lHwFcDowSDY8GNE7xbYC4YccnTo5vACPcBGAYYCw/s320/fig8.png)

* N well formation  
![fig9](https://1.bp.blogspot.com/-Rf9yUtBKM9w/Xn4ZY-ZsM7I/AAAAAAAAAlU/lN3k8jEh-zopJogYhRpk8FJkzbfgAkwTgCPcBGAYYCw/s400/fig9.png)

* After removing photoresist adn etch SiO2, N well created in p-type substrate  
![fig10](https://1.bp.blogspot.com/-AGrwAzJcBN0/Xn4ZWk5vSPI/AAAAAAAAAlU/fqWsgDqnJPMdrG61LsK0Z83WOxVlssmXQCPcBGAYYCw/s400/fig10.png)

* Deposition of polysilicon  
![fig11](https://1.bp.blogspot.com/-1Yz78QSD4O0/Xn4ZWl0K5qI/AAAAAAAAAlg/eb9cacx3t3A4gwybBZARAbZZdprHUB8IACPcBGAYYCw/s400/fig11.png)

* N diffusion and P diffusion  
![fig12](https://1.bp.blogspot.com/-MTdMJmMhNls/Xn4ZWqEkH7I/AAAAAAAAAlc/E0iRxB3Y_zcPWSj3xvnI6zv9QuS0z6sFgCPcBGAYYCw/s400/fig12.png)

* Metallization  
![fig13](https://1.bp.blogspot.com/-hxP4sX4g6Cs/Xn4ZXV8FTcI/AAAAAAAAAlo/_uUOZQISTS4eOZjWg6QGFg032G6x6jgbgCPcBGAYYCw/s400/fig13.png)

* Assign the terminal of NMOS and PMOS  
![fig14](https://1.bp.blogspot.com/-zlX9RYQP-pE/Xn4ZX0i2IYI/AAAAAAAAAlk/2gbbevlums0kFDYsFy54xZvwx0-5p9fZgCPcBGAYYCw/s400/fig14.png)

</details>

</details>  

## Assignment - Fabrication Process and Layout
<details><summary> Fabrication Process and Layout Assignment </summary>  

[PDF - Fabrication Process and Layout Assignment](https://drive.google.com/file/d/1vbWfWf-7M4tKgTVmRouwW9HEL88RB4ri/view?usp=drivesdk)
</details>
