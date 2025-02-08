# Nasscom-vsd-soc-design-program

# Contents

# Day 1 : Inception of open-source EDA, OpenLANE and Sky130 PDK 

* How to talk to computers

* Introduction to QFN-48 Package, chip, pads, core, die and IPs

*  Introduction to RISC-V

*  From Software Applications to Hardware

* SoC design and OpenLANE

* Introduction to all components of open-source digital asic design

* Simplified RTL2GDS flow

* Introduction to OpenLANE and Strive chipsets

* Introduction to OpenLANE detailed ASIC design flow

* Get familiar to open-source EDA tools

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

Basic Linux Commands:

cd : opens the particular folder

ls : lists the content of the folder

pwd : shows the present working directory

mkdir : to make a new directory

command --help : shows the complete use that command

clear : clears the terminal screen


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

* Started as an Open-source flow for a true open-source Tape-out Experiment.

* Strive is a family of open everything SoCs 

        * open PDK ,Open EDA ,open RTL.

* The Main Goal of openlane is produce a clean GDSII with no human intervention.(n0-human-in-the-loop)

# Introduction to opnlane detailed Asic design flow 

![image](https://github.com/user-attachments/assets/f5eb0c1c-f4ab-4602-a1d3-0f2c0915033e)


* The above flow diagram shows the openlane asic flow ,it has several steps.



# DAY 1 LAB REPORTS : 



# DAY 2 :  Good floorplan vs bad floorplan and introduction to library cells

* Chip Floor planning considerations

* Utilization factor and aspect ratio

* Concept of pre-placed cells

* De-coupling capacitors

* Power planning

* Pin placement and logical cell placement blockage

* Steps to run floorplan using OpenLANE

* Library building and Placement

* Netlist binding and initial place design

* Optimize placement using estimated wire-length and capacitance

* Final placement optimization

* Need for libraries and characterization

* Congestion aware placement using RePlAce

* Cell design and characterization flows

* Inputs for cell design flow

* Circuit design steps

* Layout design step

* Typical characterization flow

* General timing characterization parameters

* Timing threshold definitions

*Propagation delay and transition time

# THEORY :


![image](https://github.com/user-attachments/assets/f516492f-125d-4c06-95ae-ae56ad23bb74)

here H= height , w = width


# Utilization Factor and Aspect Ratio

Utilization Factor : It is the area occupied by the netlsit to the total area of the core.

* when the utilization factor is 1 that is 100% ,which means the core is completely occupied by the logic.

  #  Utilization Factor = Area Occupied by the netlsit / Total area of the core.

Aspect Ratio : height of core diveded by width of core

* When aspect Ratio is 1 it indicates that the chip is square shape. when aspect ratio is other than 1,indicates that the chip is rectangular shape.
  
# Aspect Ratio = height / width


![image](https://github.com/user-attachments/assets/404a3d9f-1b33-49a0-a03f-961ded64627b)



Let's put the dimensions we have, we get

Utilization factor = 4*1sq.unit / 4unit *2unit = 0.5

So, utilization factor = 0.5 (It signifies Rectangle shape)

Aspect Ratio = Height / width = 2 unit / 2unit = 1

Whenever Aspect Ratio is 1 it signifies that chip is square shaped. When it is not 1 it means the chip is in rectangular shape.

![image](https://github.com/user-attachments/assets/cd143dd9-0077-4ac2-b656-0b5f7c2774e0)


so the design will look like above image


# Pre-palced cells : 
Blocks have user-defined locations,and hence are placed in chip before automated placememt-and-routing and are called as pre-placed cells.


# De-coupling Capacitors

![image](https://github.com/user-attachments/assets/56fc86f1-dd29-4336-918e-8b7886c94039)

Consider the amount of switching current required for a complex circuit something like above

1.consider capacitance to be zero for the discussiion. Rdd,Rss,Ldd and Lss are well defined values.

2.During switching operation ,the circuit demands switching current i.e peak current (I peak)

3.Now,due to the presence od Rddand Ldd,there will be a voltage drop access them and the voltage at Node 'A would be Vdd' instead of Vdd. 

# Noise Margin :

** If Vdd goes below the noise margin ,due to Rdd and Ldd ,the logic '1' at the output of circuit wont be detected as logic '1' at the input of the circuit following this circuit  

![image](https://github.com/user-attachments/assets/cdc9474d-0edc-4da6-b9f6-3d4f6fb5c90f)

We soleve this problem using by adding De-coupling Capcacitors 

sol: 1. Addition of Decoupling Capacitor in parallel with the circuit .

2.Every time the circuit switches,it draws current from Cd, whereas ,the RL network is used to replenish the charge into Cd.


![image](https://github.com/user-attachments/assets/9924785a-396d-4d0d-84bb-0147c6fd7cea)

* The above image is the adding de-coupling capacitor to the design.
  
![image](https://github.com/user-attachments/assets/8032b1a4-f123-41ba-8da8-baf6e232b661)


# POWER PLANING 


![image](https://github.com/user-attachments/assets/fa75b881-2b1a-4963-8297-721004d07ac2)

The below image is the power mesh creation 

![image](https://github.com/user-attachments/assets/1d5b94f2-132d-472e-916d-ad15217d7087)

# Pin Placement 

lets take the below example for pin placement 

![image](https://github.com/user-attachments/assets/e85f42d4-9dca-4a1a-b3dc-c07e69d89f98)

* The inputs ports of pin placement is done at left hand side

* And the output ports of pin placement is done at right hand side 

![image](https://github.com/user-attachments/assets/bc2ff279-d230-4727-ab6c-5f403daafc3d)


# PLACEMENT 

![image](https://github.com/user-attachments/assets/280b3314-412c-411c-86eb-4ea985e2a8bf)

# Optimized Placement 

** Optimized placement is the stage  where we estimate wire length and capacitance and,based on that ,insert repeators.

![image](https://github.com/user-attachments/assets/8df3d08e-abc2-47e3-b45a-2b88f03407f2)

# LIBRARY CHARACTERIZATION AND MODELLING 

* Part 1 :Concepts and theory - NLDM ,CSS timing,power and noise characterization  

1 . In this the frist one is "LOGIC SYNTHESIS" ,in this the RTL code converted into optimized gate level netlist.

![image](https://github.com/user-attachments/assets/8c80928e-593c-4a02-ac58-f3490452fa8e)

2. second one is "FLOORPLAN",in this it decides the core and die size. these sizes completely dependent on the gates of netlist 

![image](https://github.com/user-attachments/assets/7b275d16-bce2-405b-a665-a4e66e1d3c95)

3.The third one is "PLACEMENT" The standrad cells are actually placed here.

![image](https://github.com/user-attachments/assets/b0f71bf1-9315-4738-b8e7-6cb91a2573be)

4. The fourth one is "CTS" .in this clock tree can be build usind clock buffers.

![image](https://github.com/user-attachments/assets/4b7831a7-35fb-476c-ba81-8990235c5afd)

5. The fivth is "ROUTING" ,in this the actual routing of design is done here.

![image](https://github.com/user-attachments/assets/a249fad1-0d3f-402f-b8e1-c23b87b8126e)

6. sixth one is "STATIC TIMIMG ANALYSIS",in this it can analyze the setup and hold timing of design.

![image](https://github.com/user-attachments/assets/3007d92a-b0dd-4c29-b07f-bb287c24356d)


# INPUTS FOR CELL DESIGN FLOW 

![image](https://github.com/user-attachments/assets/e3d81266-a92a-477c-8428-5111148bbf10)

fom above we look an example of inverter cell view 

*Mainly cell view can be divided into 3 parts i.e : 1)inputs  2) Design steps  3)outputs

1) Inputs : Process Design Kit (PDK), DRC&LVS rules, SPICE Models .library & user-defined specs     

![image](https://github.com/user-attachments/assets/c134eed9-8611-4d70-a099-a809dc581128)

2) Design Steps :: circuit design ,layout design, characterization


![image](https://github.com/user-attachments/assets/16649e97-b8fc-4337-9c96-6c2f364cd4cb)

* Layout Design :

![image](https://github.com/user-attachments/assets/7bb60642-3a72-4817-997f-72164e2fe24c)


![image](https://github.com/user-attachments/assets/593427f5-8c1d-4de9-9699-8300eb339ad8) 

* Characterization flow :

![image](https://github.com/user-attachments/assets/f5e336da-2dea-4cba-9032-460b50e7622c)


* Timing Characterization :
  a) 

  ![image](https://github.com/user-attachments/assets/ef70b0e5-ff95-4e0a-bc5e-8c0dbf922cef)


3) Outputs : CDS(  circuit Description Language) , GDSII ,LEF , Extracted Spice Netlsit (.cir) ,Timing , Noise , Power .libs ,function.

















































