# Nasscom-vsd-soc-design-program

# Contents

# Day 1 : Inception of open-source EDA, OpenLANE and Sky130 PDK 
# *How to talk to computers
* Introduction to QFN-48 Package, chip, pads, core, die and IPs
*  Introduction to RISC-V
*  From Software Applications to Hardware
# *SoC design and OpenLANE
* Introduction to all components of open-source digital asic design
* Simplified RTL2GDS flow
* Introduction to OpenLANE and Strive chipsets
* Introduction to OpenLANE detailed ASIC design flow
# * Get familiar to open-source EDA tools
* OpenLANE Directory structure in detail
* Design Preparation Step
* Review files after design prep and run synthesis
* OpenLANE Project Git Link Description
* Steps to characterize synthesis results

# Theory  

  ![image](https://github.com/user-attachments/assets/bbbea715-3de3-447d-983f-6a4519a9265e)

Pads:
It is used to send signal from inside and outside of the chip.

Die :
It is the place where chip is present.

Core :
It is the place where logical gates and connections are present.




![image](https://github.com/user-attachments/assets/b79095ba-c361-4322-95e0-166a7575ed1c)

The Entire Design starts from Architecture and it can be implemented by  RTL to layout. 


*EDA TOOLS:
![image](https://github.com/user-attachments/assets/bde5b9ef-1a30-442c-8098-ff73d634637f) 


# *ASIC(Application Specific Integrated circuit) Design Flow:

This flow starts from RTL to GDSII,and it is also called automated PnR and /or physical implementation.

# *RTL to GDS FLOW

![image](https://github.com/user-attachments/assets/cfe1cd01-37ea-4fb8-82b5-821a51bfcdad)


* SYNTHESIS :

It is the process of converting High level description language into technology mapped gate level Netlist using Standard cell library.

![image](https://github.com/user-attachments/assets/bcbf04b1-4a5a-468c-bc79-46bcfc2457fa)

* Each cell have regular layout.

* Each have different views /models 
 
          * Electrical,HDL,SPICE,
          
          * layout ....


* FLOORPLAN AND POWERPLAN:

1)chip floorplaning: 

* partioning the chip die between different system building blocks and place the I/O pads.

* Macro floorplaning : Dimensions,pin locations,rows definition.

2)Powerplaning:

![image](https://github.com/user-attachments/assets/b8051e58-79d4-4c01-9366-d79f213332f0)

* PLACEMENT: 
 
 place the cells on the floorplan rows,aligned with the sites

* It can be usually done in 2 steps i.e Global Placement and Detailed Placement.

![image](https://github.com/user-attachments/assets/4817881a-2728-4023-a441-5605f7e97f70)


* CLOCK TREE SYNTHESIS(CTS):

Create a clock tree distribution network
          * to deliver the clock to all sequential elemnet (e.g:flip flops) 
          * with minimum skew(zero is hard to achieve)
          * And in agood shape 
          * Usually a tree(H,X...)
  
  ![image](https://github.com/user-attachments/assets/a4d6d5b9-fde0-44c4-877d-e6ed8d556af7)

* ROUTING :

Implementing the internal connections using the available Metal layers

![image](https://github.com/user-attachments/assets/18cc7bf4-09da-492e-b8b1-745ba66f2047)

* Metal Tracks from a routing grid
* routing grid is huge
* Devide and conquer 
  * Global Routing : Generates routing guides.
  * Detailed Routing:uses the routing guides to implement the actual wiring.

* SIGN OFF:

* Physical verifications:
  -Design Rule check (DRC)
   -layout vs Schematic (LVS)
  
* Timing Verification:
  - Static Timing Analysis(STA)
    
# Introducing OPENLANE :

Started as an 
