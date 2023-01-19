# Intel_CKT_Training

## Table of contents
+ **[ Day 1 - Fundamental of VLSI Design & Overview of Sand-to-Silicon ](https://github.com/xinniteo/Intel_CKT_Training#day-1)**
  <details><summary> Theory </summary>  
  
  [Theory - Fundamental of VLSI Design & Overview of Sand-to-Silicon](https://github.com/xinniteo/Intel_CKT_Training/blob/main/README.md#theory---fundamental-of-vlsi-design-&-overview-of-sand---to---silicon)
  </details>
  <details><summary> Prerequisite Assignments (TBD) </summary>  
 
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
 
 + **[ Day 3 - CMOS Fabrication Process in DSM and UDSM Technology ](https://github.com/xinniteo/Intel_CKT_Training#day-3)**
   <details><summary> Theory </summary>  
  
   [Theory - CMOS Fabrication Process in DeepSubmicron (DSM) and Ultra DeepSubmicron (UDSM) Technology](https://github.com/xinniteo/Intel_CKT_Training#theory---analog-vlsi-design-flow--cmos-fabrication-process)
   </details>
   <details><summary> Assignment </summary>  

   
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

----------------------------------------------------------------
## Day 3
## Theory - CMOS Fabrication Process in DeepSubmicron (DSM) and Ultra DeepSubmicron (UDSM) Technology
<details><summary> CMOS Fabrication Process </summary>

### **CMOS Fabrication Process**
<details><summary> Disadvantage of the Submicron CMOS Process </summary> 
  
#### Disadvantage of the Submicron CMOS Process
* transistor size decreases causing reverse bias pn junctions to isolate transistors becomes impractical
  * due to p-well and n-well getting nearer  
* ![image](https://user-images.githubusercontent.com/121996016/212166563-52e82ff0-d6d7-4a05-9dae-0e071364420b.png)

</details>  

<details><summary> Local Oxidation of Silicon (LOCOS) Isolation Process </summary> 
  
#### Local Oxidation of Silicon (LOCOS) Isolation Process
* a traditional isolation technique used in submicron processes
* Pros: simple process flow and high oxide quality as whole LOCOS structure is thermally grown
* Cons: bird’s beak effect and surface area that lost to this encroachment
1. Pad oxide which is a very thin layer silicon dioxide is grown on the wafer.A layer of silicon nitride is then deposited to use as an oxide barrier  
![image](https://user-images.githubusercontent.com/121996016/212791271-c9ca3e06-d01a-4cd1-b634-5ddef373c1e4.png)
2. Photolithography is done to pattern and etch the nitride and pad oxide where the thick oxide will be grown  
![image](https://user-images.githubusercontent.com/121996016/212791450-408695d5-54e4-4113-9b6d-fa8176b0c502.png)
3. A thick oxide is grown in the exposed area through y thermal oxidation process  
![image](https://user-images.githubusercontent.com/121996016/212791493-d9176804-d28a-4774-8eee-91719805ae22.png)
4. Last step is the removal of the silicon nitride layer  
![image](https://user-images.githubusercontent.com/121996016/212791591-2cdaffa8-8bc8-41e2-9c4a-8592f9ca6d2f.png)
  
</details> 
  
<details><summary> Sallow Trench Isolation Technology </summary> 
  
#### Sallow Trench Isolation Technology
* allows closer spacing of transistors by eliminating the depletion region at the surface and Bird’s beak effect due to LOCOS process  
![image](https://user-images.githubusercontent.com/121996016/212791893-6d319513-6afe-4d3f-be3d-74a28427f56e.png)
* isolation process for deep-submicron process because it completely avoids Bird’s beak shape characteristics
* Pros: more suitable for the increased density in a small area because it allows forming smaller isolation regions
* Cons: larger number of process steps
1. Wafer is covered with pad oxide and silicon nitride  
![image](https://user-images.githubusercontent.com/121996016/212792228-300ca197-91fe-4195-9afb-f75f1465b533.png)
2. Nitride and pad oxide are etched. An anisotropic etch is then made in the silicon to a depth of 0.4 to 0.5 microns  
![image](https://user-images.githubusercontent.com/121996016/212792288-afb0f410-b5e0-49b4-abf7-ab586e2d2759.png)
3. A thin thermal oxide layer is grown on the trench walls  
![image](https://user-images.githubusercontent.com/121996016/212792333-5a6e2d0d-0c5a-4f9b-82e2-4451e1a42b1c.png)
4. The trench is then filled with a Chemiccal Vapour Deposition (CVD) dielectric film  
![image](https://user-images.githubusercontent.com/121996016/212792402-689d9b42-1aca-44cb-9805-8fe5e7e19100.png)
5. The dielectric layer is polished back until the nitride is reached through Chemical Mechanical Polishing (CMP) step  
![image](https://user-images.githubusercontent.com/121996016/212792486-3ee50c1f-d855-4696-b9a8-0033ddfbbf4f.png)
6. The dielectric material is densified at 900°C and the nitride and pad oxide are striped  
![image](https://user-images.githubusercontent.com/121996016/212792536-23faf8ba-62ca-4b1a-9aa1-c5aed2715680.png)

</details> 
  
<details><summary> Illustration of a Deep Submicron (DSM) CMOS Technology </summary> 
  
#### Illustration of a Deep Submicron (DSM) CMOS Technology
![image](https://user-images.githubusercontent.com/121996016/212711297-14f63543-dfae-49f8-9ba8-eb56084baa12.png)
* There is oxide layer between metal 
* Between metal layer is connected with copper
* We have no controll on the thickness of layer, only length and width
  * from cross section of an IC, it can be seen that metal routings in lower layers have a smaller thickness
  * Keeping them ‘thinner’ than the upper layers is essential to decrease parasitic capacitances because they are closer to the substrate. 
  * Higher metal layer -> thickness increases -> larger cross section area -> smaller resistance  
  ![image](https://i0.wp.com/www.electricalvolt.com/wp-content/uploads/2020/11/resistance-formula.jpg?resize=473%2C395&ssl=1)
* Therefore, normally the top metal layer is the power routing
  * to make sure that there is minimum voltage drop across them
  * thicker higher metal layer is also affordable since it does not contribute too much parasitic capacitance, as it is at a greater height from the substrate
* Middle metal layer is the signal routing, clock routing and etc.  
  
* To the NMOS and PMOS transistor, the DSM technology able to: 
  * reduce substrate noise coupling through deep n-well
  * make voltage controlled oscillators (VCOs) through a MOS varactor(capacitance varies based on voltage)
  * With minimum 6 levels of metal that can form many useful structures such as inductors, capacitors, and transmission lines
  * provide different resistors:  
    • Diffused and/or implanted resistors  
    • Well resistors  
    • Poly resistors  
    • Metal Resistors  
    • ![image](https://user-images.githubusercontent.com/121996016/212729808-12fc8343-c488-48df-9e01-f4f143779ce5.png)

* Different Types of Capacitor in Deep Submicron (DSM) CMOS Technology  
![image](https://user-images.githubusercontent.com/121996016/212743945-7c8d367c-6af2-423d-98a4-7bb237cb5c38.png)
  
* Example of a DSM Technology Process (SKY130)
![image](https://user-images.githubusercontent.com/121996016/212754265-01272cb0-f3eb-4760-b7af-e3f354ad87f2.png)
  
</details>

<details><summary> Typical Deep Submicron (DSM) CMOS Fabrication Process </summary> 
  
#### Typical Deep Submicron (DSM) CMOS Fabrication Process  
Starting Material
* a highly doped substrate to act as a good conductor
* ![image](https://user-images.githubusercontent.com/121996016/212783825-f57b1432-e1e8-4aa5-9e3c-792ecdaee11b.png)

Step 1: n and p-well Creation
* p-well in NMOS and n-well in PMOS are fabricated through implantation followed by a deep diffusion  
* ![image](https://user-images.githubusercontent.com/121996016/212786422-eb311685-58d0-45bd-8604-fc0cf904e4bb.png)
  
Step 2: Sallow Trench Isolation
* to isolate one region/transistor from another
* ![image](https://user-images.githubusercontent.com/121996016/212786600-b514b4c9-d01d-4a22-a16e-f0e77941b373.png)

Step 3: Threshold Shift and Anti-Punch through Implants
* natural thresholds of NMOS around 0V ; PMOS around -1.2V
  * An p-implant is used to make :
    * NMOS harder to invert
    * PMOS easier resulting in threshold voltages balanced around zero volts
* an implant can be applied to create a higher-doped region beneath the channels
  * to prevent punch-through from drain depletion region extending to source depletion region
* ![image](https://user-images.githubusercontent.com/121996016/212787101-b91b70e8-da8d-4aba-8d3c-0641b5bdcfa0.png)
  
Step 4: Threshold Shift and Anti-Punch through Implants
* a thin oxide is deposited followed by polysilicon
  * unwanted area are removed
* ![image](https://user-images.githubusercontent.com/121996016/212787306-418db099-4361-4a01-9311-4408274505f8.png)
  
Step 5: Lightly Doped Source and Drain
* a lightly-doped implant is used to create a lightly-doped source and drain next to the channel of the MOSFETs
* ![image](https://user-images.githubusercontent.com/121996016/212787409-4f4f3d89-5641-4023-afc5-7facb010cfb9.png)
  
Step 6: Lightly Doped Source and Drain
* a layer of dielectric is deposited on the surface and removed
  * to leave “sidewall spacers” next to the thin-oxide-polysilicon-polycide sandwich
    * sidewall spacers will prevent the part of source and drain next to the channel from becoming heavily doped
* ![image](https://user-images.githubusercontent.com/121996016/212787723-f6efcd65-ccba-49f9-b184-5efdd3747dee.png)
  
Step 7: Implantation of Havily Doped Source and Drain
* to provide the completed sources and drains
* to allow ohmic contact into the wells and substrate
* ![image](https://user-images.githubusercontent.com/121996016/212787953-931754d5-5e4c-4d37-9526-9d84b75f01d9.png)

Step 8: Siliciding (Salicide and Polyside)
* to reduces the resistance of the bulk diffusions and polysilicon
* to form an ohmic contact with material on which it is deposited
* ![image](https://user-images.githubusercontent.com/121996016/212788106-297a7f50-dce9-4919-b818-049cd18b8832.png)

Step 9: Intermediate Oxide Layer
* to cover the transistors
* to planarize the surface
* ![image](https://user-images.githubusercontent.com/121996016/212788276-47974670-6927-4492-a168-e44d7bdfd6e8.png)
  
Step 10: First Level Metal
* Tungsten plugs are built through the lower intermediate oxide layer
  * to provide contact between the devices, wells and substrate to the first-level metal
* ![image](https://user-images.githubusercontent.com/121996016/212788516-eb69a961-35a0-4b57-81f4-3c47cad3d27a.png)
  
Step 11: Second Level Metal
* previous step is repeated for the second-level metal
* ![image](https://user-images.githubusercontent.com/121996016/212788670-53b25580-13d9-4ce1-ad8e-1afc646f92e9.png)
  
![image](https://user-images.githubusercontent.com/121996016/212788751-5ce275f1-dc69-47ad-a9cc-337d51cb4ebb.png)

</details>

<details><summary> Summary of Deep Submicron (DSM) CMOS Fabrication Process </summary> 
  
####  Summary of Deep Submicron (DSM) CMOS Fabrication Process
DSM Technology 
* typically has a minimum channel length between 0.35μm and 0.1μm
* addresses the problem of excessive depletion region widths in junction isolation techniques by using shallow trench isolation
* may have from 4 to 8 levels of metal
* lightly doped drains and sources are one of the key aspects

</details>
  
<details><summary> Ultra Deep Submicron (UDSM) CMOS Technology </summary> 
  
####  Ultra Deep Submicron (UDSM) CMOS Technology
* Lmin ≤ 0.1 um
* minimum feature size < 100 nm
* Today’s state of the art:
  * 22 nm drawn length
  * 5 nm lateral diffusion (12 nm gate length)
  * 1 nm transistor gate oxide
  * 8 layers of copper interconnect
* specialized processing is used to increase drive capability and maintain low off currents                
* ![image](https://user-images.githubusercontent.com/121996016/212790473-bc7b1e79-885d-481c-be2d-882df2332a9f.png)
                            
</details>
  
  
  
  
  
     
</details>   

## Assignment - DSM and UDSM Fabrication Process
<details><summary> DSM and UDSM Fabrication Process Assignment </summary>  

 <!---[PDF - DSM and UDSM Fabrication Process Assignment]()-->
</details>

