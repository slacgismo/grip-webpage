---
title: "Analytics"
draft: false
math : true
---
# test 
# hello world 
### Table of contents for Anticipation, Absorption, and Recovery Models and Model Outputs
*[Anticipation]*
1. [Anticipation Solar Disaggregation Model](#disaggregation)
2. [Disaggregation Model Input Steps](#inputsteps)
3. [Outputs of Disaggregation Model](#outputs)
4. [Solar Disaggregation Utility Application](#utility)
5. [Solar Disaggregation Utility Application Outputs](#utilityouputs)
6. [Anticipate AMI DATA Meter Clustering](#ami)
7. [Anticipate-Microgrid Design Tool-Pole Model](#microgrid)
8. [Pole Loading Due to Pole Tilt Angle](#poleloading)
9. [Mounted equipment loading due to pole tilt](#poletilt)
10. [Anticipate DER Analytics](#der)
11. [Anticipate Outage Cost Analysis](#outage)
12. [Anticipate- Smart Switching](#smart)
13. [Vegetation Impact Analysis](#vegetation)
14. [Vegetation Fall](#fall)

*[Absorption]*
1. [GRIP Absorption/virtual islanding](#islanding)
2. [GRIP Absorption/virtual islanding constraints](#constraints)
3. [Identifying Loops](#loops)
4. [GRIP Absorption/island management algorithm](#islandmanagement)
5. [GRIP Absorption/island management algorithm constraints](#utilityouputs)

[Recovery]
1. [Recovery Simulations](#recovery)







## Anticipation  

*Anticipate Load Disaggregation Model*

#### **Goal**:

##### *Perform disaggregation on collected data using publically available appliance labeled data for model training to inform consumers of their consumption habits, and develop better load models for distribution planning activities*

#### **Methods Used**:
##### open-source tool (NILMTK) and the REDD data set from MIT to train models for disaggregation prediction and validate performance given known labels

### *Functional Capabilities of the model*              

-Breaks down provided power consumption                 
data from a given meter into the constituent
appliances.

-Uses training data to make accurate
predictions and returns overall
appliance level disaggregation and a
disaggregation over time.


-Users can use provided sample training and
test data or upload their own as CSV files

-Utilizes the open source NILM toolkit for a
bulk of the data analysis processing

-Can inform consumers who are
using a ton of energy about
their consumption patterns.

-Can lead to better load models for
distribution planning

### *Load Disaggregation Mechanism*

1.  Gridlab-D is used to simulate loads
and meter data for a single household

2. 90% of the data is used as training
data for NILMTK disaggregation
algorithms

3. NILMTK makes a prediction on the
remaining 10%

4. Predictions are compared to the
simulated ground truth to quantify
prediction errors

However, as demonstrated below in *Figure 1*, NILMTK predictions
are very inaccurate.


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/ANT_FIGURE_DEL6_3.png)
##### **Figure 1**: However, NILMTK alternatives have been used and model results are represented below with *Figure 2 below*:


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/ANT_FIGURE_DEL6_3_PT_4.png)
##### **Figure 2**

*Disaggregation is potentially feasible using this model*




### **1. Anticipation Solar Disaggregation Model**

Solar Disaggregation model CSSS integrated in to OMF code
base. (CSSS = Contextually Supervised Source Separation).
CSSS gives utilities the ability to detect solar installations on their
systems that were not disclosed to the utility

*2. Steps of Model Inputs:*

1.  User uploads 3 .csv files, enters a start date, and selects
an ASOS station
2.  Net load for each house measured at 15 minute intervals
3.  Solar proxy load measured at 15 minute intervals
4. Latitude/Longitude coordinates for each house and solar
proxy (ASOS station-based on the nearest city)


*3. Model outputs:*

-Temperature data points from ASOS station and
temperature interpolated to 15 minute intervals for CSSS

-Line graph of solar proxy load input

-Line graph of each net load, with hidden solar and
estimated actual load from CSSS disaggregation

-Leaflet.js map with marker clusters for each net load
source, solar proxy, and ASOS station

### **4. Anticipation Solar Disaggregation Utility Application**

CSSS is the disaggregation of a time series of source signals from
observations of their sum. CSSS gives utilities the ability to detect solar installations
on their systems that were not disclosed to the utility.

*5. Model outputs:*

-Temperature data points from ASOS station and temperature
interpolated to 15 minute intervals for CSSS

-Line graph of solar proxy load input

-Line graph of each net load, with hidden solar and estimated actual
load from CSSS disaggregation

-Leaflet.js map with marker clusters for each net load source, solar
proxy, and ASOS station

### **6. Anticipate AMI DATA Meter Clustering**

The goal meter data clustering is to
quantitatively identify relative kWh consumption
patterns that are shared by subsets of utility
customers.

-The K-means clustering algorithm is used to
group meters together based on how their
relative consumption varies during the day.

-By identifying kWh consumption patterns, we
can help utilities perform market segmentation to
optimize how they serve customers.

-The initial investigation shows that we can
qualitatively identify meaningful, distinct
consumption patterns.

-The result of fitting four clusters to the data is
shown below in *figure 3*. This suggests that there are at least four
daily consumption patterns that are distinct to be considered market segments


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/ANT_FIGURE_METER_AMI_DEL6_3.png)
##### **Figure 3**: *AMI Meter Clustering*

### **7. Anticipate-Microgrid Design Tool-Pole Model**

##### *Goal:* Due to  the ability of a load to shape over a 1yr time period determine what combination of solar, wind, and batteries increases resiliency and minimizes cost.

##### **Methods:**

 The basic method of evaluating the condition of a pole relative to ground-line structural failure is to calculate the resisting moment at ground level and compare that with the total moment from the loads present.  

The resisting moment for a wood pole at the ground line is computed as:

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/IMG_1.png)

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/ANT_USECASE_TABLE_1.png)
**Table 1**: NESC Table 261-1A Safety Factors


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/ANT_USECASE_TABLE_2.png)
**Table 2**: Ultimate Fiber Stress of Selected Wood Products


Pole degradation is modeled by computing the rate at which the interior is hollowed out by rot. The hollow interior diameter grows at the rate R such that the interior hollow diameter is given by ![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/IMG_2.png), (where Y is the age of the pole). When considering pole degradation, the resisting moment is  

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/IMG_3.png)

*Note*: Ground line failure assumption ignores the possibility that the hollow interior diameter may lead to failure at the midpoint of the pole or at the pole top near the superstructure.


### **8. Pole Loading Due to Pole Tilt Angle**

The pole failure model in GridLAB-D has been updated to support the extended Grid Resilience Intelligence Platform (GRIP) use case for the *HiPAS Project (CEC EPC-17-046)*. Utility structures are analysed while accouting for presence of conductors, equipment, hardware, miscelaneous cables and extreme weather. The pole failure model in GridLAB-D is designed to examine multiple failure modes. However, given that ground-level structural failures are reported as the most frequent, the current implementation only supports these. Other failure modes are under current implementation and will be available in future versions of HiPAS GridLAB-D.



Detailed implementation and methodology in the following sections. 

##### Ground-level Failure
A pole can fail at or near the ground line due to excessive forces on the structure.  The following forces are considered:
- Pole loading due to pole tilt angle
- Mounted equipment loading due to pole tilt
- Wire weight loading due to pole tilt angle
- Wind pressure on pole
- Wind loading due to wind pressure on mounted equipment
- Wire loading due to wind pressure on wire
- Wire ice loading
- Loading due to wire tension asymmetry
- Critical wind speed for pole failure
- Pole failure probability under wind gust
- Wire sag loading due to sag asymmetry *Future work*
- Wire loading due to line sway *Future work*
- Wire loading due to line gallop *Future work*

##### Superstructure Failure 
Since the resisting moment for the utility pole superstructure will drop as the diameter of the pole decreases, a pole may fail above the ground owing to the reduced resisting moment. The SLAC team currently works on the development and validation of pole superstructure loading analysis considering pole shear force, bending moment and pole stress.
##### Other Failures
Other failure modes are possible, such as foundation failures and equipment malfunction. These are not considered at this time.

##### Methodology

The basic method of evaluating the condition of a pole relative to ground-line structural failure is to calculate the resisting moment at ground level and compare that with the total moment from the loads present.  
The resisting moment for a wood pole at the ground line is computed as follows:


$$M_R = 0.008186S_fF_bD_0^3$$
in ft.lb, where \\( S_f \\) is the NESC Table 261-1A safety factor (see Table 1), \\( F_b \\) is the fiber strength (see Table 2)and \\( D_0 \\) is the ground-line diameter of the pole in inches.

Pole degradation is modeled by computing the rate at which the interior is hollowed out by rot.  The hollow interior diameter grows at the rate R such that the interior hollow diameter is given by \\( D_R=2 Y R \\) where Y is the age of the pole.  When considering pole degradation, the resisting moment is  
	$$M_R=0.008186 S_f F_b (D_0^3-D_R^3)$$
Note that the ground line failure assumption ignores the possibility that the hollow interior diameter may lead to failure at the midpoint of the pole or at the pole top near the superstructure.

Table 1. NESC Table 261-1A Safety Factors \\( (S_f) \\)
| Application      | Grade B | Grade C |
| ----------- | ----------- | ----------- |
| Rule 250B (normal conditions)           |
| Wood Structures   | 0.65        | 0.85 |
|Support structures | 1.00 | 1.00 |
|Rule 250C (extreme conditions) |
|Wood Stuctures | 0.75 | 0.75|
|Support structures | 1.00 | 1.00|

Table 2. Ultimate Fiber Stress of Selected Wood Products \\((F_b) \\)
|Species | Fiber Stress (psi) |
| ----------- | ----------- |
|Southern Yellow Pine | 8,000|
|Douglas Fir | 8,000|
|Lodgepole Pine | 6,000|
|Western Larch| 8,400|
|Western Red Cedar | 6,000|

When guy wires are present, the height at which the moments are calculated is determined by the attachment point of the guy wires rather than the ground line. The remainder of the methodology requires computing the contributions of the various loads to the total pole moment.
Note that wind induced moments may not be in the same direction as the pole tilt. The incident angle of the wind must be considered with respect to the pole tilt angle such that \\( \beta = \beta_T-\beta_W \\).  The vector sum of the moments must be used, e.g.,
	$$M=\sqrt(M_T+M_Pcos\beta)^2+(M_Psin\beta)^2$$	
In some cases, the wind pressure may reduce the tilt moment and in other cases it may increase it.

##### Pole loading due to pole tilt angle

A tilted pole is illustrated in Figure 1, where \\(H\\) is measured in ft, \\(D_0\\), and \\(D_1\\) are measured in inch and \\(M\\) is measured in ft.lb. 

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/ANT_USECASE_POLE_LOADING.png)


For small angles \\(\alpha\\), the moment resulting from the tilt of a pole of uniform diameter \\(D\\) and height \\(H\\) is
	$$M_{PT}=0.5 m H sin\alpha$$
where m is the mass of the pole in lbs. The mass m of the pole can be calculated using the density \\(\rho\\) of the material, e.g., \\(35 lb/ft^3\\), such that \\( m = (D/2/12)^2 H \rho =0.001736 \pi D^2 H \rho \\). 
However, the taper of the pole must be considered, in which case the moment is
	$$M_{PT}= sin\alpha \int_0^H h m(h) dh $$
where m(h) dh is the mass at the height h, such that \\(m(h)= \roe \pi r(h)^2 \\) with r(h) measured in ft. The resulting moment is	
$$r(h)=0.5 [D_0-(D_0-D_1) h/H]$$
$$M_{PT}= 0.125\rho \pi H^2\[1/6(D_0+D_1)^2+1/3D_1^2]sin\alpha$$

##### Mounted equipment loading due to pole tilt
Equipment mounted on a tilted pole may induce small changes in the moment depending on the position relative to the pole's centerline and the tilt direction.  The moment of equipment mounted offset from the pole's centerline is
	$$M_{ET}= W X_E$$	
where \\(W\\) is the weight of the equipment in lbs and \\(X_E\\) is the offset distance in ft.  Denote the equipment mounted direction as \\(\beta_E\\) and mounted height as \\(H_E\\), when the pole is tilted at an angle  and the pole tilt direction is \\(\beta_T\\), the tilt equipment offset distance is

$$X_{E_x}= (cos^2(\beta_T)*cos(\alpha)+sin^2(\beta_T))*X_E*cos(\beta_E)+(cos(\beta_T)*sin(\beta_T)*cos(\alpha)-cos(\beta_T)*sin(\beta_T))*X_E*sin(\beta_E)+cos(\beta_T)*sin(\alpha)*H_E$$

$$X_{E_y}= (cos(\beta_T)*sin(\beta_T)*cos(\alpha)-cos(\beta_T)*sin(\beta_T))*X_E*cos(\beta_E)+(sin^2(\beta_T)*cos(\alpha)+cos^2(\beta_T))*X_E*sin(\beta_E)+sin(\beta_T)*sin(\alpha)*H_E $$

Then the moment \\(M_O\\) and tilt mounted height \\(H_{E_T}\\) is
$$M_{ET}= W \sqrt(X_{E_x}^2+X_{E_y}^2)$$


$$H_{ET}=-sin(\alpha)*X_E*(cos(\beta_T)*cos(\beta_E)+sin(\beta_T)*sin(\beta_E))+cos(\alpha)*H_E$$













### **10. Anticipate DER Analytics**

-Automated screening process to assess
impacts of DERs on resilience/reliability
of arbitrary distribution circuits.

-Visualizations for load flow analysis

-Supplementary sortable tables for flicker,
reverse power flow, thermal, short circuit,
and fault current violations

-Allows distribution engineers to
discover problems with the DER without
expending resources in manual
interconnection modeling (multiple
power flows and circuit changes
calculated automatically).

### **11. Anticipate Outage Cost Analysis**



*Objectives*

-Visualize outage data over the
period of a year (with filtering
based on duration, date the
outage occurred, meters
affected, and cause of the
outage)

-Calculate the reliability metrics
associated with the outage
data and a feeder system
specified by an .omd file

-Generate a new set of
outages and calculate the
reliability metrics and graph
this new data (with filtering as
well)

 **Methods implemented:**

-Leaflet (geoJSON format).
-Lattice heat map (for outage
location generation)
-Scipy distributions (for outage
duration generation)

*Test data Used*

1. Olin Barre Fault

2. ieee37nodeFaultTester

-Data generation and visualization methods
can be used to help utilities predict the
distribution of future faults and associated
reliability metrics.

-The variety of different fault generation
methods that can be employed give
utilities the freedom to fine-tune
parameters based on expected
dependencies between variables (location,
cause, fault type, start time, and duration)
that become inputs to other resilience
models.

-Core XAIXI calculations are useful for
validation of other models that impact
these metrics.

### **12. Anticipate- Smart Switching**

*Objective:*

Provide utilities with a way to measure
the benefit of adding a recloser to a
distribution circuit on a given line.

The model generates random faults throughout
the period of one year given some fault
distribution and a maximum outage length,
then compare SAIDI/SAIFI/MAIFI values
and outage costs generated from the
original circuit and from the circuit with an
added recloser (taking into account a
threshold for what is classified as a
sustained outage).

*Tools used:*

1. GridLab-D.

2. Random fault generator.

3. Reliability metrics object.

4. Plot.ly for graphing.

*Test data Used:*

 test_ieee37nodeFaultTester.glm

There is evidence that adding a
recloser to a distribution circuit can help cut
costs in both residential and commercial
areas, depending on the placement of the
recloser. It is useful to run the model multiple
times with the same input data, in order to take
account the potential variance of outages in a
given year.

### **13. Vegetation Impact Analysis**

Grid resilience is affected in part by vegetation contacting or falling onto power lines during significant weather events. GridLAB-D can model the probability of vegetation events through the use of simplified models that can scale easily based on the pole vulnerability method implemented for wind analysis in the DOE Grid Resilience Intelligence Platform (GRIP).


The impact of vegetation on power lines arises from two types of wind-driven events:

*1. vegetation contact with lines*(which results in a fault)

*2. vegetation fall onto lines* (which results in an outage)

 In GridLAB-D, a fault results in a momentary loss of service (momentary is defined according to *IEEE Standard 1366*, which lasts less than 5 minutes. An outage however, is a non-momentary loss of service (lasting 5 or more minutes).

 Vegetation may contact when it has grown into the right of way enough to contact an uninsulated power line when the wind blows hard enough to cause both to deflect sufficiently. The following factors below must be considered:
1. Wind speed, V (ft/s)

2. Right-of-way distance, D (ft)

3. Vegetation growth rate, R (ft/y)

4. Elapsed time since right-of-way was maintained, ∆t (y)

5. Vegetation susceptibility as wind speed increases, S (s)

6. Line length, L (ft)

Vegetation contact with the lines is possible given deflection in both sagging lines and susceptible vegetation. When the sum of the two deflections exceeds the open space between the vegetation and lines, then momentary contact becomes probable. The deflection of sagging power lines as a function of wind speed, line length, and air temperature is

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/VEG_CONTACT_1.png)

 where y is the observed line sag at the midpoint between the poles, w is the line weight in N/m, and the perpendicular wind force in N/m is

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/VEG_CONTACT_2.png)

 where d is the line diameter in meters, and the β is the line windage coefficient in s/m^2.
 The deflection of vegetation as a function of susceptibility and wind speed is approximated as
 ![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/VEG_CONTACT_3.png)

 The open distance between the line and vegetation is approximated as:
 ![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/VEG_CONTACT_4.png)

 The probability of contact is determined by the ratio:

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/VEG_CONTACT_5.png)

When the ratio *RC ≥ 1.0* then contact with an uninsulated power line is certain and will cause a momentary fault.

### **14. Vegetation Fall**

Vegetation may fall onto power lines when it has aged sufficiently and is stressed due to drought. Vegetation must have grown into the right-of-way so that the probability of fall is function of:

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/VEG_FALL_1.png)


and the critical wind speed V:
![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/VEG_FALL_2.png)

where A is the age of the tree. The probability of a line outage from vegetation fall is then:

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/VEG_FALL_3.png)





## **Absorption**   

Members of the LBNL team in employed 2D-ES control for managing active and reactive power contributions of DER on a distribution network for minimizing voltage phasor difference across an open or closed switch. The LBNL team performed multiple validation simulations using the GRIP platform (allows for easy simulation setup and execution). The LBNL team used the IEEE 37 node test feeder for the simulated distribution network. A multitude of varying objective and control configurations were tested. Simulations show that ES control of distributed resources is a viable method for minimization voltage difference between adjacent and connected buses, or disconnected buses.

### **1. Objectives of GRIP Absorption/virtual islanding**

-minimize the value-weighted amount of unserved load
-ensure that we maintain as much reserve as possible to account for future load increases.
-maximize the batteries state of-charge at the final time step
-minimize the number of switching events and the total number of loads that are “on” for reserves accounting

### **2. Constraints**

The following are the constraints used in the VIIP model.


![Absorbance constraints equations](/AB_CONSTRAINTS_EQUATIONS.png)
 Equation 2.7  ensures that power supply and demand balance.

 Equation 2.8  ensures that power supply and demand balance, after having factored in the reserves.


Equations 2.9 and 2.10 limit power the line flows to be zero if a switch on the link is open, or to be within limits if the switch is closed (or non-existent).

Equation 2.11 shown below limits power generation to be within limits and Eq. 2.11 limits power generation to be within limits for the reserves case.

Equations 2.13  and 2.14 limit the load to be within limits in the base case and in the reserves case.

Equations 2.15 and 2.16 limit the battery power to be within limits for both cases. Equations 2.17 and 2.18 limit the battery energy state to be within limits in the base case and in the reserves case.

Equations 2.19 and 2.20 calculate the battery energy state of one time step, dependent on the previous time step energy and power values in the base case and in the reserves case.

 Equation 2.21 ensures that after all switching operations are complete, the distribution network remains radial. Equation 2.22 ensures that R (the reserves variable) is less than or equal to the amount of surplus in the virtual island with the smallest amount of reserves. Equation 2.23 ensures that the binary state variables are indeed binary.

### **3. Identifying Loops**

*Requirements for solving VIIP*

*Step 1*:  Know the location of loops within the distribution network- see equation 2.21 from above
*Step 2*: Begin at a randomly selected node in the circuit, and include this node in the set of visited nodes. Call this node, node s, and the set of all visited nodes V
*Step 3*: Identify the neighbors of node i: Ni.

 *Note*: If all of the nodes in Ni have been previously visited, quit (end point found). If there are only two nodes in V randomly select one of the nodes in Ni that are not in V , call this node i, add it to V and repeat. If there are more than two nodes in V and the only node in Ni that is not in V is s, then quit (loop of length three or more nodes has been found; repeat from step 1). If there are more than two nodes in V and s is not in Ni, then advanced to a randomly chosen node in Ni that is not in V and repeat this step.

### **4. Objectives of GRIP Absorption/island management algorithm**

 -minimize the value-weighted amount of total unserved (shed) non-flexible energy.
 -ensure that we maintain as much battery energy at the end of the time horizon as possible
 -maximize the virtual battery energy at the end of the time horizon.
 -maximize the value-weighted level of customer comfort over the entire time horizon.

### **5. Constraints**

The following are the constraints used in the IMO model.


![Absorbance constraints equations](/AB_CONSTRAINTS_EQUATIONS_PART_2.png)

Equation 2.30  ensures that power supply and demand balance over the entire time horizon. Equations 2.31 limit power the output for the solar and non-solar generators.

Equation 2.33 limits batteries power to be within limits and Equation 2.34 limits the setpoint for the virtual battery to be within a reasonable range for the flexible devices. Equation 2.35 limits the load shedding to be within the range of non-flexible load from the baseline timeseries. Equations 2.36 and 2.40 limit the energy state to be within limits for the batteries and virtual battery. Equations 2.37, 2.38, 2.41, and 2.42 model the batteries and virtual batteries energy state over the time horizon.

The output of the optimization is a time-series of setpoint values and the resulting state of-charge of the batteries and virtual battery over the entire time horizon of 24-hours. The figures below shows this output for the optimization of the initial time step of the simulation for both the "fire" represented by *Figure 4* and "ice" represented by *Figure 5* test cases.


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/AB_FIGURE2_6OPTIMAL_OUTPUT_FIRE.png)
##### **Figure 4** *Fire Output*


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/AB_FIGURE_2_6OPTIMAL_OUTPUT_ICE.png)
##### **Figure 5** *Ice Output*


### **Absorbance- FLISR**

**Goal:**

Quickly isolate a fault and restore power in a  
distribution system by opening and closing switches  
already present in the system.

### **Methods implemented:**

-Adjacency list representation of connectivity
-Maximal connected subgraphs
-Depth-first search
-Test Data:Modified Oline Barre Fault (with 16 initially  
open tie lines and 15 initially closed reclosers)

 The FLISR algorithm provides  sub-second restoration for a system with ~3000 nodes, and a proof is provided that the solution is optimal for both radial and non-radial feeder systems.  

*(The algorithm has the potential to drastically reduce the amount of time it takes to find an optimal solution and implement it in a faulted system).*

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/AB_FLISR_1.png)
##### **Figure 6**: Beginning to solve a system with our algorithm

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/AB_FLISR_2.png)
##### **Figure 7**: Continuing to find a solution


### **Absorbance (ML) Forecasting**

**Goal:**: provide open, free load forecasting methods  
to utilities. Forecasts basis of many load control  
and energy storage dispatch tasks, and these  
tasks are critical in resilient design and restoration  
activities.

###  **Methods implemented:**

-Artificial Neural Network

-Rolling Time-series Regression (ARIMA)

-Double Exponentially Smoothed ARIMA

-Daily Peak Support Vector Regression

-Test data: ERCOT North Region 2002–06

In summary:
**Strong results for all methods, neural network forecast had clearest day-ahead hourly MAPE success (2.58%)**

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/AB_FORECAST_1.png)
##### **Figure 8**: representation of neural network plot and daily peak demand forecast

A utility may decide to invest in batteries or a direct load control program to improve system resilience; however, these efforts are only as effective as the utility’s ability to predict the day’s energy consumption. Forecasting methods we developed were integrated in to a model giving statistical likelihood that tomorrow will be the monthly peak.

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/AB_FORECAST_2.png)
##### **Figure 9**:Representation of testing on ERCOT data where the model could find a once-weekly dispatch strategy that would only miss the monthly peak every few years





## **1. Recovery**

The Extremum Seeking approach has been tested in hardware in the loop experiments and in live field tests. The LBNL team performed multiple validation simulations using the GRIP platform. The LBNL team used the IEEE 37 node test feeder for the simulated distribution network. A multitude of varying objective and control configurations were tested. Simulations show that ES control of distributed resources is a viable method for minimization voltage difference between adjacent and connected buses, or disconnected buses. *The GRIP platform allows easy simulation setup and execution.*

*Figure 1* below shows a block diagram of the overall ES architecture for multiple 2D-ES controllers managing active and reactive power contributions of distributed energy resources (DERs). In this use case, the objective represents a distribution network, measurements of pertinent system states, and computation of a value that the 2D-ES controllers operate to minimize. A single 2D-ES controller is encircled by the red box, with its active power channel is encircled by the green box, and its reactive power channel is encircled by the blue box. In the figure below, LPF stands for lowpass filter, HPF stands for high pass filter, and INT denotes the integrator.


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_ES.png)

#### **Figure 1**:*Two dimensional Extremum Seeking Control (2D-ES) loop for simultaneous control of DER active and reactive power.*


Demonstrated below (*figure 6*) is a simulation that was performed using the GRIP platform. The simulated network was the IEEE 37 node test feeder, and GridLab-D was used to solve power flow.


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_2_FINAL_REPORT.png)
##### **Figure 6**  illustrates the topology of the IEEE 37 node test feeder. The objective of the simulation was to minimize the total voltage phasor difference between bus 709 and bus 708 (which were connected during the experiment).


Single phase four quadrant inverters were placed at the following phases and buses: 703-A, 703-B, 703-C, 733-A, 733-B, 733-C (see figure 2). Each inverter was managed by an 2D-ES controller (2D-ESC) with both active power and reactive power probes. All 2D-ESCs utilized a sinusoidal probe for both their active and reactive power probes, all with a unique frequency on the order of 0.1 Hz, for both its active power and reactive power probe. All 2D-ESCs had a constraint on the magnitude of inverter active power of 100 kW, a constraint on the magnitude of inverter reactive power of 100 kVAr, and a constraint on inverter apparent power of 100 kVA. All ESCs had an active power probe magnitude of 10 kW, and a reactive power probe magnitude of 10 kVAr.


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_3_FINAL_REPORT.png)
##### **Figure 7** represents the objective function, defined above, over the course of the 10 minute simulation. The objective function is reduced from a value of roughly 210 to roughly 50.


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_4_FINAL_REPORT.png)
##### **Figure 8** shows the phase a voltage magnitude difference between bus 709 and 708, and the phase a voltage angle difference between bus 709 and 708. The figure demonstrates that the voltage magnitude difference is reduced, as is the voltage angle difference.


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_5_FINAL_REPORT.png)
##### **Figure 9** shows the phase b voltage magnitude difference between bus 709 and 708, and the phase b voltage angle difference between bus 709 and 708. The figure demonstrates that the voltage magnitude difference is reduced, as is the voltage angle difference.


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_6_FINAL_REPORT.png)
##### **Figure 10** plots the phase c voltage magnitude difference between bus 709 and 708, and the phase c voltage angle difference between bus 709 and 708. The figure demonstrates that the voltage magnitude difference is reduced, as is the voltage angle difference.


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_7_FINAL_REPORT.png)
##### **Figure 11** plots the active and reactive power contributions of the inverter on phase a at bus 703. This figure shows the ESC was limited by its maximum apparent power constraint.


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_8_FINAL_REPORT.png)
##### **Figure 12** shown above plots the active and reactive power contributions of the inverter on phase a at bus 733. This figure shows that the ESC was limited by its maximum apparent power constraint.

### **Recover Anomaly Loading**:

**Goal:** detect equipment failure and/or non-technical losses from meter data streams.

### **Methods implemented:**

-Facebook Prophet
-Daily Peak SVM T-Test
-Local Outlier Factor (LOF)
-Isolation Forests
-Symbolic Approximation (SAX) - Sequitur

**Test data:**

1. ERCOT South Region 2002–05
2. Synthetic data from GridLAB-D


*Near perfect identification of theft and hardware failures when test/train split on same meter, however cross-training results are pending*

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_ANOMALY_1.png)
##### **Figure 13**

### **Recovery Fast Anomaly**:

**Goal:** 1. Detect equipment failure (residential, transformer) and non-tech losses from meter data; 2. implement methods with sub-hour train/test performance to enable realtime detection
### **Methods:**

-Local Outlier Factor (LOF)

-Isolation Forests

-Symbolic Approximation (SAX) - Sequitur

-SVM

Test Data:

1. Tagged datasets from utilities uncommon

2. Generated test data using 2 utility circuits and
GridLAB-D

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_ANOMALY_2.png)
##### **Figure 14**


### **Recovery Anomaly Fast Detection Validation**

1. Detection methods are found to be reliable with 6 months of training data.

2. Scores lower for cross-trained models(train on one meter, test on another)

3. Future work will focus on cross-trained test case because this is the likely deployment method (single meter methods would only detect further issues on that 1 meter).

4. Non-technical losses frequently confused with other anomalies, so we're redefining how this anomaly is defined

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_ANOMALY_3.png)
##### **Figure 15**: 6 month Olin Barre GH test case

### **Recovery Network Structure Learning:**

**Goal:** Find the likely connectivity of a feeder system, given the location information for each node and some voltage data

### **Methods implemented:**

-Prim’s Algorithm (find minimal spanning trees)

-scikit-learn SVM model

**Test data:**

1. ieee37nodeFaultTester

2. test_ieee123nodeBetter

3. Taxonomy Feeders

4. Distance data is obtained from the .omd file and
voltage data from running GridLAB-D on the .glm

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_ANOMALY_4.png)
##### **Figure 16**

*Connectivity can be approximated with very good accuracy for smaller feeder systems. Further work must be done in making sure the model is viable for any arbitrary system*

### **Recovery Black Start**:

**Goal:** Find a sequence of energizing generators and opening/closing switches that restores power in a transmission network and an effective means of visualizing the sequence using powerflow.

**Methods Implemented:**

-pandapower

-NetworkX

**Test Data:**

1. Randomly generated transmission networks

 We can find the best possible path to black start a transmission network and verify our results by running powerflow with pandapower (restoration sequence bottom right seen in **figure 17** below ).

Using NetworkX, we can visualize the results of powerflow at each step of blackstart where, for each node, size is the power generation and color is the power demand. The arrows in the graph represent the *direction of current flowing* and the *width* of the edges show how much power is transferred from one node to another (powerflow results top right).

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_BLACK_START.png)
##### **Figure 17**
