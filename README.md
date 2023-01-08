# Intel_CKT_Training

## Table of contents
+ **[ Day 1 - Overview of VLSI Design ](https://github.com/xinniteo/Intel_CKT_Training#day-1)**
  <details><summary> Theory </summary>
  
  [Theory - Overview of VLSI Design](https://github.com/xinniteo/Intel_CKT_Training/blob/main/readme.md#theory---Overview-of-VLSI-Design)
 
## Day 0
## Theory - Overview of VLSI Design
<details><summary> Chip-to-wafer </summary>
  
### Packaged Chip
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

### Die and Wafer
* generally die size is (1x1)mm or (1x2)mm
* wafer diameter is around 12 inch ~ 300 mm
* a single wafer contains 10’s of thousands die  

   </details>
  
<details><summary> Overview of Inside the Die </summary>
  
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
  
* Moore’s Law defines the number of transistors in a dense integrated circuit doubles every 2 years
  * Every two years, the feature size is reduced by 1/sqrt(2) times

   </details>

<details><summary> VLSI Design Methodology </summary>
  
### Despite of different design style, proper functionality, low cost and timely execution is much more important
### Two types of VLSI Design Styles:
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
  
### Importamt criteria to measure the design quality:
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
  
  
