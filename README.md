# 5 DAYS WORKSHOP TOPICS

# Day 1 : Inception of open-source EDA, OpenLANE and Sky130 PDK 

# Contents

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


# Basic Linux Commands:

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


# SYNTHESIS :

It is the process of converting High level description language into technology mapped gate level Netlist using Standard cell library.

![image](https://github.com/user-attachments/assets/bcbf04b1-4a5a-468c-bc79-46bcfc2457fa)

* Each cell have regular layout.

* Each have different views /models 
 
          * Electrical,HDL,SPICE,
          
          * layout ....


  # FLOORPLAN AND POWERPLAN:

1)chip floorplaning: 

* partioning the chip die between different system building blocks and place the I/O pads.

* Macro floorplaning : Dimensions,pin locations,rows definition.

2)Powerplaning:

![image](https://github.com/user-attachments/assets/b8051e58-79d4-4c01-9366-d79f213332f0)

# PLACEMENT: 
 
 place the cells on the floorplan rows,aligned with the sites

* It can be usually done in 2 steps i.e Global Placement and Detailed Placement.

![image](https://github.com/user-attachments/assets/4817881a-2728-4023-a441-5605f7e97f70)


# CLOCK TREE SYNTHESIS(CTS):

Create a clock tree distribution network
        
          * to deliver the clock to all sequential elemnet (e.g:flip flops) 
          
          * with minimum skew(zero is hard to achieve)
          
          * And in agood shape 
          
          * Usually a tree(H,X...)
  
  ![image](https://github.com/user-attachments/assets/a4d6d5b9-fde0-44c4-877d-e6ed8d556af7)

# ROUTING :

Implementing the internal connections using the available Metal layers

![image](https://github.com/user-attachments/assets/18cc7bf4-09da-492e-b8b1-745ba66f2047)

* Metal Tracks from a routing grid

* routing grid is huge

* Devide and conquer 

  * Global Routing : Generates routing guides.

  * Detailed Routing:uses the routing guides to implement the actual wiring.


# SIGN OFF:

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

OpenLane is an automated RTL to GDSII flow based on several components including OpenROAD, Yosys, Magic, Netgen, CVC, SPEF-Extractor, KLayout and a number of custom scripts for design exploration and optimization. The flow performs all ASIC implementation steps from RTL all the way down to GDSII.

![image](https://github.com/user-attachments/assets/f5eb0c1c-f4ab-4602-a1d3-0f2c0915033e)


* The above flow diagram shows the openlane asic flow ,it has several steps.



# DAY 1 LAB REPORTS : 

# Design Preparation steps

# openlane

![image](https://github.com/user-attachments/assets/3759afb9-445a-4140-832a-3ae61331d831)

![image](https://github.com/user-attachments/assets/311a83b9-1db0-4206-b8f2-ff87eb4b17fa)

* The Next step is Run the synthesis 

# Run Synthesis

![image](https://github.com/user-attachments/assets/3482a33f-0824-41f1-b91d-07418b78171d)



# STA report
![image](https://github.com/user-attachments/assets/b6ed72f6-c3a5-48cf-8420-7716fcdb2343)

![image](https://github.com/user-attachments/assets/6d6a2849-80cc-4715-8bdb-ec3315c8ab42)


In below it contains information of number of wires and cells in design

flop ratio = Toatal number of cells / Total number of flipflops 

flop Ratio = 1613/14876 = 0.1084

![image](https://github.com/user-attachments/assets/a37ff018-1b7a-4d45-b445-ae9642af066a)

# Synthesis Result

![image](https://github.com/user-attachments/assets/3feaaa17-1eb0-4bf2-b746-7a6b5e8f83b2)

![image](https://github.com/user-attachments/assets/94f0f50b-ec21-4177-bbaa-8e09f31ace04)

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

![image](https://github.com/user-attachments/assets/920ef075-b8d6-4f2e-9808-775ad0de7218)


a)Timing Thresh hold
  
 ![image](https://github.com/user-attachments/assets/ef70b0e5-ff95-4e0a-bc5e-8c0dbf922cef)

 b) Popogation Delay 

 ![image](https://github.com/user-attachments/assets/8c0f20c4-b2c1-44af-ba32-f27f91ef09de)


![image](https://github.com/user-attachments/assets/ea920050-44b1-4b18-a787-be517bb47eb0)

c)Transition Time 

 ![image](https://github.com/user-attachments/assets/7d930e4a-97ea-4f28-9b39-82c24b51cb84)

![image](https://github.com/user-attachments/assets/f0e7b7b6-9b28-4bb0-8c42-b29e6bea99bf)

d)Output current Wave form 

3) Outputs : CDS(  circuit Description Language) , GDSII ,LEF , Extracted Spice Netlsit (.cir) ,Timing , Noise , Power .libs ,function.



# Day 2 LAb REPORTS

The Next step after synthesis is floorplan

Run the floorplan using the command run_floorplan

![image](https://github.com/user-attachments/assets/4f407ae6-3912-42da-b72b-a881414e3499) 

![image](https://github.com/user-attachments/assets/225c2d08-d5eb-4fcb-9a36-052477425657)


![image](https://github.com/user-attachments/assets/2a2686b0-3005-4b94-b07b-ee033418fa68)

![image](https://github.com/user-attachments/assets/3f18339d-40eb-4131-9905-bd7ba9317a94)

After run the floorplan we have one def file i.e picorv32a.floorplan.def

![image](https://github.com/user-attachments/assets/68d23bfa-e41a-4cc7-afd6-775addc89728)

![image](https://github.com/user-attachments/assets/4c56fe23-8295-4bef-ba2b-19faac8c12b5)

In above the die area = (0 0)  (660685  671405)

1 micron=1000 database units

width=660685/1000 = 660.685

height = 671405/1000 = 671.405

# Floorplan Layout in Magic

![image](https://github.com/user-attachments/assets/2214e2dc-c540-4dcb-af36-c593e69fb670)
 
![image](https://github.com/user-attachments/assets/4293643a-589f-4e26-97b2-08c0d9f0e1d1)


# Palcement 
 
after floorplan next step is placemnet 

run the placement by using the command 'run_placement' 

Placement : Placement is the stage where the standard cell placement can be fixed.

In placement there are two steps 

1)Global Placemet: It is nothing but coars placement

2)Detailed placement : It is nothing but legalized placement


![image](https://github.com/user-attachments/assets/9e0cb3e8-6f9b-4e85-b19c-16eda4b017b1)

![image](https://github.com/user-attachments/assets/3bebdde8-54cf-4eaa-a1b4-c01b31f1dbf9)

# congestion aware placemnet using Replace 

![image](https://github.com/user-attachments/assets/478dd6a4-e6a9-4b07-bec5-2f002b3eb135)

![image](https://github.com/user-attachments/assets/81d25b85-4663-4e76-992d-92f23329f998)

![image](https://github.com/user-attachments/assets/63ecddf9-79e0-4cb8-8a38-da26d39930a1)

# Day 3 : Design library cell using Magic Layout and ngspice characterization

Content:

 * Labs for CMOS inverter ngspice simulations

* IO placer revision

* SPICE deck creation for CMOS inverter

* SPICE simulation lab for CMOS inverter

* Switching Threshold Vm

* Static and dynamic simulation of CMOS inverter

* Lab steps to git clone vsdstdcelldesign

* Inception of layout ̂A CMOS faabrication process

* Create Active regions

* Formation of N-well and P-well

* Formation of gate terminal

* Lightly doped drain (LDD) formation

* Source and drain formation

* Local interconnect formation

* Higher level metal formation

* Lab introduction to Sky130 basic layers layout and LEF using inverter

* Lab steps to create std cell layout and extract spice netlist

* Sky130 Tech File Labs

* Lab steps to create final SPICE deck using Sky130 tech

* Lab steps to characterize inverter using sky130 model files

* Lab introduction to Magic tool options and DRC rules

* Lab introduction to Sky130 pdk's and steps to download labs

* Lab introduction to Magic and steps to load Sky130 tech-rules

* Lab exercise to fix poly.9 error in Sky130 tech-file

* Lab exercise to implement poly resistor spacing to diff and tap

* Lab challenge exercise to describe DRC error as geometrical construct

* Lab challenge to find missing or incorrect rules and fix them

# Theory

# SPICE deck creation for CMOS inverter :

![image](https://github.com/user-attachments/assets/02c22f23-2800-4f80-bf39-2f794d7f4148)

![image](https://github.com/user-attachments/assets/b5ce9e89-0c86-4337-a880-8e4f7533a4e2)

![image](https://github.com/user-attachments/assets/7994c749-6c99-46c2-b349-576ac983d17b)


![image](https://github.com/user-attachments/assets/df5889e4-8809-4480-854f-03ea6b0df727)

![image](https://github.com/user-attachments/assets/1484ff84-2dff-4df3-93b5-fa75662d214a)

![image](https://github.com/user-attachments/assets/03f7892f-b006-4c20-84a1-3d0381f82105)

# Create Active Region:

Active Region is the place where we see CMOS & NMOS 

# 16-Mask CMOS process 

1) Selecting a substate

2) Creating Active Region for Transistors

![image](https://github.com/user-attachments/assets/78c05a97-332e-43d0-ba2f-dcdb69f9a58b)

![image](https://github.com/user-attachments/assets/0a6dd8c3-8cf2-467c-86fd-6549b8b3c56d)

* Removing Mask

![image](https://github.com/user-attachments/assets/bea49926-dcca-48fb-8cfc-f3f632b92356)

* Removing Photoresist

![image](https://github.com/user-attachments/assets/fc2cc71a-e714-475a-88dd-52554aca0ecf)

*Removing silicon Nitrate 

![image](https://github.com/user-attachments/assets/3d33873a-efe5-4e1a-96f5-749c867b55a4)


3) N-Well and P-Well formation :

Top view of Mask 2

![image](https://github.com/user-attachments/assets/9e433286-75ba-4918-9883-392cae7f863a)

![image](https://github.com/user-attachments/assets/782f1d81-a492-47ca-a60d-c5ec83620c5a)

* Boron is a P-type it creates a P-Well,which needs high energy needed for creating P-Well

 ![image](https://github.com/user-attachments/assets/01936a71-63c6-4014-a7c5-497358ad7a1e)

![image](https://github.com/user-attachments/assets/045852c1-a934-4ada-be19-3bbd6d2c92bc)

![image](https://github.com/user-attachments/assets/7e1db51b-c86c-4b96-b843-59e7e89d2ec7)

4 ) Creating Gates :

![image](https://github.com/user-attachments/assets/c3ddc58f-1720-4baf-a461-900961922b3c)
 
![image](https://github.com/user-attachments/assets/6d563a6e-002f-463d-8f19-705d7a8711a4)

![image](https://github.com/user-attachments/assets/4b8408b2-7342-4724-8909-fd444e6acd6e)

![image](https://github.com/user-attachments/assets/36f7d7a3-5797-4c84-9b61-e3e3a392417f)

* Top View of Gate Mask 6

![image](https://github.com/user-attachments/assets/d9b13790-2d16-47ad-b72b-b1fe430e1f82)


5) Lightly dopped drain (LLD) formation

![image](https://github.com/user-attachments/assets/b203e62c-a52d-4cdf-96fa-e185cec97ae9)

![image](https://github.com/user-attachments/assets/a42d2451-59eb-4d3d-a745-2fde1f2a5860)

![image](https://github.com/user-attachments/assets/4bcced79-5632-4b28-9f4c-d95edc97f864)

![image](https://github.com/user-attachments/assets/6e233960-7b25-4fc5-aa5a-8112ab625b9d)

![image](https://github.com/user-attachments/assets/53f2c95e-38e7-43ef-99ad-dbd3a7e16227)

![image](https://github.com/user-attachments/assets/ed79ac4b-9006-4479-a773-a04a38dcee5c)

6) Source And Drain Formation

![image](https://github.com/user-attachments/assets/5bbb61d7-809d-4739-a3d5-c2ef1ed551e3)

![image](https://github.com/user-attachments/assets/c4b8f1f6-8e37-4fd1-9b18-2f961a2522d3)

![image](https://github.com/user-attachments/assets/c4c1e785-30d0-47f2-9a6c-6cc17e008f15)

![image](https://github.com/user-attachments/assets/12b1d14a-1d29-4f7a-86df-00d5ff744cf6)

![image](https://github.com/user-attachments/assets/1fdf418c-73e8-434c-9627-d74758b0cdeb)

7) steps to form contacts and interconnects (local) 

 * Deposite titanium on wafer surface, using sputtering 

![image](https://github.com/user-attachments/assets/fdbdc5ec-5747-4850-9d4a-7969117e5f3a)

![image](https://github.com/user-attachments/assets/c47ed4d2-d528-4e7a-824a-80721a55b48c)

![image](https://github.com/user-attachments/assets/ade3381d-25c3-4762-b9ff-220766b3dc4d)

![image](https://github.com/user-attachments/assets/f3a668f4-f468-4303-8e99-5f97ea394fa8)

* TiN is etched using RCA cleaning

![image](https://github.com/user-attachments/assets/8c545865-8a06-4279-9299-0374fb9dd861)

![image](https://github.com/user-attachments/assets/74c1311d-538c-4f19-8b7c-f2ee558abb9d)

![image](https://github.com/user-attachments/assets/646030a9-f028-49de-9817-431c952eda44)


8) Higher level metal Formation

![image](https://github.com/user-attachments/assets/37a93098-3604-41d1-889f-4cc92d6bfaa2)

![image](https://github.com/user-attachments/assets/5aa78065-f32b-45b0-aa6b-2ac6cab3e23a)

![image](https://github.com/user-attachments/assets/67d185f9-7ad5-4226-8635-65237a160d5a)

![image](https://github.com/user-attachments/assets/7dd08b17-4126-4ffe-8c59-2c0431ef5c31)

![image](https://github.com/user-attachments/assets/fd96be8e-839a-4ca7-88de-a6748564762e)

![image](https://github.com/user-attachments/assets/3d32bd17-47cf-4d08-a6ab-2fccaf6dce82)

![image](https://github.com/user-attachments/assets/441643d3-1b10-4573-a9a1-40df2c1df70a)

![image](https://github.com/user-attachments/assets/55165152-2c5e-49a6-b982-179f76f284bb)

![image](https://github.com/user-attachments/assets/07ba6b2e-5c82-4119-905c-bd7e372804e5)

![image](https://github.com/user-attachments/assets/d2691d3c-c722-4615-995b-a0f4d921fbb2)

# Day 3 LAB Reports

IO PLACER Rivision:

![image](https://github.com/user-attachments/assets/5704e9fe-b170-4633-821b-d7e48b9b6176)

# LAB STEPS TO GIT CLONE VSDSTDCELL DESIGN

![image](https://github.com/user-attachments/assets/69748ce0-b679-4f75-a540-60ab62e0f50d)

# Load the custom inverter layout in magic

![image](https://github.com/user-attachments/assets/3d872b1b-f54a-41d4-bd08-df0081de5c8a)


![image](https://github.com/user-attachments/assets/147bc2fb-868c-4ac0-8b6f-5ab0d5cba9e5)

![image](https://github.com/user-attachments/assets/387d8422-dde7-464c-bda8-5b29b5e14499)

# Extract spice Netlist

![image](https://github.com/user-attachments/assets/9730a4a6-73be-4a6b-bdaf-be57a4cc90a0)


![image](https://github.com/user-attachments/assets/04d7e957-7d12-4fc1-83ea-99648a16cadf)


# Create final SPICE desk using sky130 tech

![image](https://github.com/user-attachments/assets/449e9736-233d-4278-bff8-32d467b6b932)

![image](https://github.com/user-attachments/assets/0fe3ef92-2055-4936-b2cd-89c739aed1f2)


# ngspice simulation

![image](https://github.com/user-attachments/assets/ffdab85b-0d90-45a7-8118-0131b384012d)

input

![image](https://github.com/user-attachments/assets/efe880cd-8c79-4e94-b80f-85735085fb6f)

output

![image](https://github.com/user-attachments/assets/b3496352-a15d-402b-ad60-9a984a5297b7)

![image](https://github.com/user-attachments/assets/c8c28dc0-07ac-4948-b35e-0e513a12e7a4)

![image](https://github.com/user-attachments/assets/504433ed-e3e1-4155-b266-77698373deee)


# DAY 4 : Timing Analysis with Real clocks using openSTA

# Contents:

* Timing modeling using delay tables

* Lab steps to convert grid info to track info

* Lab steps to convert magic layout to std cell LEF

* Introduction to timing libs and steps to include new cell in synthesis

* Introduction to delay tables

* Delay table usage Part 1

* Delay table usage Part 2

* Lab steps to configure synthesis settings to fix slack and include vsdinv

* Timing analysis with ideal clocks using openSTA

* Setup timing analysis and introduction to flip-flop setup time

* Introduction to clock jitter and uncertainty

* Lab steps to configure OpenSTA for post-synth timing analysis

* Lab steps to optimize synthesis to reduce setup violations

* Lab steps to do basic timing ECO

* Clock tree synthesis TritonCTS and signal integrity

* Clock tree routing and buffering using H-Tree algorithm

* Crosstalk and clock net shielding

* Lab steps to run CTS using TritonCTS

* Lab steps to verify CTS runs

* Timing analysis with real clock using openSTA

* Setup timing analysis using real clocks

* Hold timing analysis using real clocks

* Lab steps to analyze timing with real clocks using OpenSTA

* Lab steps to execute OpenSTA with right timing libraries and CTS assignment

* Lab steps to observe impact of bigger CTS buffers on setup and hold timing

# Theory

![image](https://github.com/user-attachments/assets/f7ba9de0-b838-43c4-a516-e8310c43c7de)

![image](https://github.com/user-attachments/assets/3d6a5f77-f34d-4517-aa48-1f3bd5ce06b2)

![image](https://github.com/user-attachments/assets/bb45c21e-5294-46bc-8aad-71ed2ab20063)

Assume c1=c2=c3=c4=25fF and Cbuf1=Cbuf2=30fF

Total Cap at node 'A'=> 60fF

Total Cap at node 'B'=> 50fF

Total Cap at node 'C'=> 50fF

Example:

![image](https://github.com/user-attachments/assets/377c7b53-a3a1-4183-8b14-772bac3a84dd)

![image](https://github.com/user-attachments/assets/a8410720-9968-4b20-b4da-d8750f1a41f1)


# Timing analysis using openSTA

![image](https://github.com/user-attachments/assets/55c90d6f-33ed-4c61-933f-b0d44554f6c0)

![image](https://github.com/user-attachments/assets/a069a99a-6e40-4748-bae5-814295cffb45)

![image](https://github.com/user-attachments/assets/52b4a7f1-cc6a-4193-8e50-783f905431c7)

![image](https://github.com/user-attachments/assets/85ab955d-00a5-4031-8fef-fbc7f141118d)


# Clock tree routing

![image](https://github.com/user-attachments/assets/3607b07e-2070-440f-bf71-76bdbbd20058)

![image](https://github.com/user-attachments/assets/17482635-52c2-4499-849f-d2beb99ec2f2)

![image](https://github.com/user-attachments/assets/d637280b-7ee7-47c7-b9bc-2c7b43e92000)


![image](https://github.com/user-attachments/assets/3ef991a2-7a0e-433d-b4d8-a22e45cfa89b)

![image](https://github.com/user-attachments/assets/1fa24129-b10d-47c4-bfc7-eccd6469060b)

# Crosstalk and Clock net shielding

![image](https://github.com/user-attachments/assets/5e71f7cf-a138-4b42-8f74-9e885f5a37ee)

![image](https://github.com/user-attachments/assets/8485bcda-6164-4b58-b7da-414fa71d4a0c)

# Setup and Hold timing analysis

![image](https://github.com/user-attachments/assets/e7e2a7b3-24ee-4bfd-8ab2-77034e1e4266)

![image](https://github.com/user-attachments/assets/c31f0805-bde6-4e44-80e1-2a98d4b6b7d6)

![image](https://github.com/user-attachments/assets/d51b6bdb-0952-45ca-b094-1bdb723ea9ca)

![image](https://github.com/user-attachments/assets/5e37f635-fed4-4ff2-b2e3-17f6ac643bb9)

# Day 4 Lab

# Lab steps to convert grid info to track info

![image](https://github.com/user-attachments/assets/3204cebd-08fa-4df7-87fd-25d488c36b9f)


![image](https://github.com/user-attachments/assets/37eb9689-c599-429d-a7dc-79919b17c208)

![image](https://github.com/user-attachments/assets/f8b3ca5c-db3a-466e-8ad9-bcdcea29c5d7)

![image](https://github.com/user-attachments/assets/7b770fba-f038-4992-b53d-d8093ad05917)

# Lab steps to convert magic layout to std cell LEF
![image](https://github.com/user-attachments/assets/d5f5f21b-4abc-41f6-ae9e-c0ce5c80eb30)

![image](https://github.com/user-attachments/assets/0930bbcb-1a92-410c-8eb6-b0120598fddb)

![image](https://github.com/user-attachments/assets/9871511c-aa32-4b71-b6ce-94de178b692d)

![image](https://github.com/user-attachments/assets/5b10938a-acdc-4b09-b27e-55d3d2e7fd80)

![image](https://github.com/user-attachments/assets/53332981-2982-4a76-b328-5f94aff24f41)

# sky130_vsdinv.lef

![image](https://github.com/user-attachments/assets/dd5ea8c8-ee15-4bda-8aa2-1ec294b3f75e)

# Introduction to timing libs and steps to include new cell in synthesis

![image](https://github.com/user-attachments/assets/f189a358-93c3-405c-956a-d59867769ba4)

![image](https://github.com/user-attachments/assets/45994b4e-79ab-4bf7-85b3-c7c1addfaea1)

# sky_130_fd_sc_hd_typical.lib

![image](https://github.com/user-attachments/assets/94aeb299-f4b4-4d54-9a97-d8ee68394a6d)

# sky_130_fd_sc_hd_slow.lib

![image](https://github.com/user-attachments/assets/8af1630b-52b2-4660-8b44-6a972abc6459)

# sky_130_fd_sc_hd_fast.lib

![image](https://github.com/user-attachments/assets/6d4c8ca6-c849-45d4-a0c2-8a6358aa94c4)


![image](https://github.com/user-attachments/assets/997fdc16-ae9f-4cb5-9479-52b07868de94)

![image](https://github.com/user-attachments/assets/55135d9d-079d-4129-aac5-1c931e96cebc)


# config.tcl file

![image](https://github.com/user-attachments/assets/4ce0a43b-a951-4109-8ae2-54512b7ce08e)

# Openlane Execution

 ./flow.tcl -interactive

 package require openlane 0.9

 prep -design picorv32a -tag 17-02_06-53 -overwrite 

set lefs [glob $::env(DESIGN_DIR)/src/*.lef]

add_lefs -src $lefs

![image](https://github.com/user-attachments/assets/960eddd5-a668-4fe8-ade3-277879fefde5)


![image](https://github.com/user-attachments/assets/e7369078-2335-4c13-badc-d1ed2d4e149d)

# run_synthesis

![image](https://github.com/user-attachments/assets/b99f45e5-1367-401d-90f3-c341cbb7eecd)

# README.md file

![image](https://github.com/user-attachments/assets/6d8d7792-1439-4064-b2e9-b59848547ce2)

# To fix slack 

![image](https://github.com/user-attachments/assets/f7047d22-7af9-4011-b065-cf6fe1f51a6d)

 * run_synthesis

 * init_ floorplan 
 
 * pace_io
 
 * tap_decap_or

![image](https://github.com/user-attachments/assets/b4ff39dd-372e-4c1b-a867-cc70800b4a81)


![image](https://github.com/user-attachments/assets/be8e623f-750f-44f6-b240-cead719fdd13)

![image](https://github.com/user-attachments/assets/fe659c91-f98d-41fc-926d-24a6ae1cc60e)

![image](https://github.com/user-attachments/assets/6b4e9bfa-c8aa-4754-9f54-d18788520895)

# Post Synthesis timing analysis with openSTA tool

Commands:

#Change directory to openlane

cd Desktop/work/tools/openlane_working_dir/openlane

#Command to invoke OpenSTA tool with script

sta pre_sta.conf

# invole sta tool by using "sta" command

![image](https://github.com/user-attachments/assets/7671521c-7d5b-4935-aa7a-2f2bb303061d)

# prep_sta.conf file 

![image](https://github.com/user-attachments/assets/6dd401e9-be16-4b47-b8dc-e92003ae6f44)

# picorv32a.sdc file 

![image](https://github.com/user-attachments/assets/2c253062-6573-4899-bcbc-de28deacd638)

# Make timing ECO fixes to remove all violations

![image](https://github.com/user-attachments/assets/fb4a61fa-847c-4ef7-b008-9ff3c8854f0b)

![image](https://github.com/user-attachments/assets/d545221a-c535-4103-ba7a-7260e96f5d7a)

![image](https://github.com/user-attachments/assets/b6f82549-bd3a-4611-b2af-5b3613177fc4)

# cell getting Replaced

![image](https://github.com/user-attachments/assets/e54aa4ac-40a5-4cfa-9160-d67c7c4a7c96)

# Before & After Slack

![image](https://github.com/user-attachments/assets/80fa4fcc-2abb-44c8-b331-49f9a6b6f95c)


![image](https://github.com/user-attachments/assets/a871efd0-776b-4f80-a83a-f5eadd172f85)

It is reduced from -5.39 to -5.33

# Replace the old netlist with the new netlist generated after timing ECO fix and implement the floorplan, placement and cts

![image](https://github.com/user-attachments/assets/a31cd4f6-2668-4fb1-b6ad-4cb8190947e9)

# Verified that the netlist is overwritten

![image](https://github.com/user-attachments/assets/6bc257f6-08bd-4f49-92a7-588c1a373758)

# Load the design and run necessary stages

![image](https://github.com/user-attachments/assets/a7b80956-64b9-4a61-867a-36e942dc7a29)


* run_synthesis

  ![image](https://github.com/user-attachments/assets/1cf5e974-9321-4f9b-b94f-4e8a15f99db2)

*init_floorplan

![image](https://github.com/user-attachments/assets/ffedc28e-e7aa-42bc-9109-5fdb258ab29f)

* place_io

![image](https://github.com/user-attachments/assets/dae953d2-05cc-4004-810f-e04729dc0d26)

* tap_decap_or

![image](https://github.com/user-attachments/assets/8f7590bc-d66f-4463-a51f-8dbf0a4234cc)

* run_placement
  

# CTS

run_cts

![image](https://github.com/user-attachments/assets/4ecd354b-e6e5-479c-a71b-63cdcaef7aa1)

# cts.tcl file

![image](https://github.com/user-attachments/assets/73bdccf8-3bfc-498b-97cf-2dabfc9090fc)


![image](https://github.com/user-attachments/assets/59c17bcb-a508-475c-b4f3-3c2aa566bc24)

#  or_cts.tcl file 

![image](https://github.com/user-attachments/assets/40ea8d8e-b945-40d7-b94b-4f7c355c3a62)

![image](https://github.com/user-attachments/assets/a26c0468-d8c5-4f47-92e5-4cb62fe4702d)

# sky130_fd_sc_hd__typical.lib file

![image](https://github.com/user-attachments/assets/a2dbd35e-5ac6-4b37-97cf-1321df931dc5)


# Post-CTS OpenROAD timing analysis

# openroad 

![image](https://github.com/user-attachments/assets/9b50d096-0d77-4dd6-a222-f43aa4ef0b04)

![image](https://github.com/user-attachments/assets/cee86f90-fe48-4958-8266-7592b0445073)

![image](https://github.com/user-attachments/assets/c907c781-7aed-440b-9c1a-56a4cc21935e)

![image](https://github.com/user-attachments/assets/2c89a9ed-4ff0-46bb-8890-ba8ee32c442d)

![image](https://github.com/user-attachments/assets/0def4e7d-2abf-4c6a-83f0-14b4b9a65872)

![image](https://github.com/user-attachments/assets/cf68f17b-96f9-4dfa-a1fa-8fff1816ab52)

# Post-CTS OpenROAD timing analysis

![image](https://github.com/user-attachments/assets/a5069124-3e93-4895-896a-1a9bf4ab7642)

![image](https://github.com/user-attachments/assets/158e55d4-faeb-418d-8d7e-2d121aab9316)



# Day 5 :Final steps for RTL2GDS using tritonRoute and openSTA

# Contents :

* Routing and design rule check (DRC)

* Introduction to Maze Routing and Lee's algorithm

* Lee's Algorithm conclusion

* Design Rule Check

* Power Distribution Network and routing

* Lab steps to build power distribution network

* Lab steps from power straps to std cell power

* Basics of global and detail routing and configure TritonRoute

* TritonRoute Features

* TritonRoute feature 1 - Honors pre-processed route guides

* TritonRoute Feature2 & 3 - Inter-guide connectivity and intra- & inter-layer routing

* TritonRoute method to handle connectivity

* Routing topology algorithm and final files list post-route

# Theory :

![image](https://github.com/user-attachments/assets/eeb4a2ce-27f6-4f36-9338-6aef1440805d)

![image](https://github.com/user-attachments/assets/d37a6214-5209-4dc8-b626-f053985b2fa0)

![image](https://github.com/user-attachments/assets/1e9b5481-c63d-40e6-b665-10d9a07907c7)

# Design rule check (DRC)

![image](https://github.com/user-attachments/assets/5095ce67-774a-4022-a81a-ae4e25c98b56)

![image](https://github.com/user-attachments/assets/df7e8e76-7857-4694-b327-ba41aad6123f)

![image](https://github.com/user-attachments/assets/85980b02-fc93-4722-b44b-375698f34118)

![image](https://github.com/user-attachments/assets/869629f7-99b9-4e5f-a777-2f121e34ba81)

# Routing

![image](https://github.com/user-attachments/assets/5d74f127-3a77-4adb-beb3-b38db4d8fb86)

![image](https://github.com/user-attachments/assets/c2275484-ce26-4c87-bfcb-e7a22bdd43d5)

![image](https://github.com/user-attachments/assets/8975e411-375e-489f-b74d-ad15f40035cf)

![image](https://github.com/user-attachments/assets/f3320f9f-8947-4374-b6d4-4562874ed973)

![image](https://github.com/user-attachments/assets/bf26306e-3978-4115-983a-fdc00a0eb654)

# Routing Topology Algorithm

![image](https://github.com/user-attachments/assets/0f9f670e-28e9-4fa0-9e59-6ae83442d54f)

# Day 5 LAB :

# Perform generation of Power Distribution Network (PDN)

gen_pdn

![image](https://github.com/user-attachments/assets/8db660e4-bf04-404f-b221-88dba83c09ab)


![image](https://github.com/user-attachments/assets/c51cba24-56f6-4bfe-9946-cf492b734a02)


![image](https://github.com/user-attachments/assets/ee69cee8-13b0-4a3e-8bf4-8b90a72af1dc)


![image](https://github.com/user-attachments/assets/9b98f757-fa68-465d-9fce-0d328d8cf5bd)


![image](https://github.com/user-attachments/assets/fb52dd3f-66f1-476b-9c82-0f7e1528731d)


![image](https://github.com/user-attachments/assets/7c29b2d4-a23c-456f-9324-c8417d8b23a9)

![image](https://github.com/user-attachments/assets/c0f07989-983b-4957-a73e-eaf502344cf8)

# Perform detailed routing using TritonRoute and explore the routed layout

run_routing

Load routed def in magic

![image](https://github.com/user-attachments/assets/bb47803f-8e99-4d6b-9b63-504bf6148be0)

![image](https://github.com/user-attachments/assets/90275467-90a7-4876-bd10-d749a6354346)

![image](https://github.com/user-attachments/assets/0600ffb2-7b16-40b4-b166-e22993f3abe0)

fastroute.guide file

![image](https://github.com/user-attachments/assets/2f5818b6-3ce9-4db7-b07f-f204dab6234e)

# Post-Route parasitic extraction

Parasitics command is already run and spef is extracted

In runs folder, where routing outputs are dumped and we'll find the SPEF there.

# Acknowledgements

Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.






















