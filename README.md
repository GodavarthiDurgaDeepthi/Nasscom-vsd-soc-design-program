![image](https://github.com/user-attachments/assets/1aac8e30-8a1c-4b5f-90de-06f9f384f910)# Nasscom-vsd-soc-design-program

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






