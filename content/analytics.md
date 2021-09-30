---
title: "Analytics"
draft: false
---

### Anticipation  

*Anticipate Load Disaggregation Model*

#### **Goal**:

##### *Perform disaggregation on collected data using publically available appliance labeled data for model training to inform consumers of their consumption habits, and develop better load models for distribution planning activities*

#### **Methods Used**:
##### open-source tool (NILMTK) and the REDD data set from MIT to train models for disaggregation prediction and validate performance given known labels

#### *Functional Capabilities of the model*              

● Breaks down provided power consumption                 
data from a given meter into the constituent
appliances.

● Uses training data to make accurate
predictions and returns overall
appliance level disaggregation and a
disaggregation over time.


● Users can use provided sample training and
test data or upload their own as CSV files

● Utilizes the open source NILM toolkit for a
bulk of the data analysis processing

● Can inform consumers who are
using a ton of energy about
their consumption patterns.

● Can lead to better load models for
distribution planning

#### *Load Disaggregation Mechanism*

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


#### **Anticipation Solar Disaggregation Model**

Solar Disaggregation model CSSS integrated in to OMF code
base. (CSSS = Contextually Supervised Source Separation).
CSSS gives utilities the ability to detect solar installations on their
systems that were not disclosed to the utility

*Steps of Model Inputs:*

1.  User uploads 3 .csv files, enters a start date, and selects
an ASOS station
2.  Net load for each house measured at 15 minute intervals
3.  Solar proxy load measured at 15 minute intervals
4. Latitude/Longitude coordinates for each house and solar
proxy (ASOS station-based on the nearest city)

#### Table of contents for Model Outputs
1. [Introduction](#introduction)
2. [Some paragraph](#paragraph1)
    1. [Sub paragraph](#subparagraph1)
3. [Another paragraph](#paragraph2)

**Model outputs:**

●  Temperature data points from ASOS station and
temperature interpolated to 15 minute intervals for CSSS

●  Line graph of solar proxy load input

●  Line graph of each net load, with hidden solar and
estimated actual load from CSSS disaggregation

●  Leaflet.js map with marker clusters for each net load
source, solar proxy, and ASOS station

#### **Anticipation Solar Disaggregation Utility Application**

CSSS is the disaggregation of a time series of source signals from
observations of their sum. CSSS gives utilities the ability to detect solar installations
on their systems that were not disclosed to the utility.

*Model outputs:*

●  Temperature data points from ASOS station and temperature
interpolated to 15 minute intervals for CSSS
●  Line graph of solar proxy load input
●  Line graph of each net load, with hidden solar and estimated actual
load from CSSS disaggregation
●  Leaflet.js map with marker clusters for each net load source, solar
proxy, and ASOS station

#### **Anticipate AMI DATA Meter Clustering**

The goal meter data clustering is to
quantitatively identify relative kWh consumption
patterns that are shared by subsets of utility
customers.

● The K-means clustering algorithm is used to
group meters together based on how their
relative consumption varies during the day.

● By identifying kWh consumption patterns, we
can help utilities perform market segmentation to
optimize how they serve customers.

● The initial investigation shows that we can
qualitatively identify meaningful, distinct
consumption patterns.

● The result of fitting four clusters to the data is
shown below in *figure 3*. This suggests that there are at least four
daily consumption patterns that are distinct to be considered market segments



![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/ANT_FIGURE_METER_AMI_DEL6_3.png)
##### **Figure 3**: *AMI Meter Clustering*

#### **Anticipate DER Analytics**

● Automated screening process to assess
impacts of DERs on resilience/reliability
of arbitrary distribution circuits.

● Visualizations for load flow analysis

● Supplementary sortable tables for flicker,
reverse power flow, thermal, short circuit,
and fault current violations

● Allows distribution engineers to
discover problems with the DER without
expending resources in manual
interconnection modeling (multiple
power flows and circuit changes
calculated automatically).

#### **Anticipate Outage Cost Analysis**



*Objectives*

●  Visualize outage data over the
period of a year (with filtering
based on duration, date the
outage occurred, meters
affected, and cause of the
outage)

●  Calculate the reliability metrics
associated with the outage
data and a feeder system
specified by an .omd file

●  Generate a new set of
outages and calculate the
reliability metrics and graph
this new data (with filtering as
well)

#### **Methods implemented:**

●  Leaflet (geoJSON format).
●  Lattice heat map (for outage
location generation)
●  Scipy distributions (for outage
duration generation)

*Test data Used*

●  Olin Barre Fault

●  ieee37nodeFaultTester

●  Data generation and visualization methods
can be used to help utilities predict the
distribution of future faults and associated
reliability metrics.

●  The variety of different fault generation
methods that can be employed give
utilities the freedom to fine-tune
parameters based on expected
dependencies between variables (location,
cause, fault type, start time, and duration)
that become inputs to other resilience
models.

●  Core XAIXI calculations are useful for
validation of other models that impact
these metrics.

#### **Anticipate- Smart Switching**

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

●  GridLab-D.

●  Random fault generator.

●  Reliability metrics object.

●  Plot.ly for graphing.

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







### **Absorption**   

Members of the LBNL team in employed 2D-ES control for managing active and reactive power contributions of DER on a distribution network for minimizing voltage phasor difference across an open or closed switch. The LBNL team performed multiple validation simulations using the GRIP platform (allows for easy simulation setup and execution). The LBNL team used the IEEE 37 node test feeder for the simulated distribution network. A multitude of varying objective and control configurations were tested. Simulations show that ES control of distributed resources is a viable method for minimization voltage difference between adjacent and connected buses, or disconnected buses.

#### **Objectives of GRIP Absorption/virtual islanding**

-minimize the value-weighted amount of unserved load
-ensure that we maintain as much reserve as possible to account for future load increases.
-maximize the batteries state of-charge at the final time step
-minimize the number of switching events and the total number of loads that are “on” for reserves accountin

#### **Constraints**

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

#### **Identifying Loops**

*Requirements for solving VIIP*

*Step 1*:  Know the location of loops within the distribution network- see equation 2.21 from above
*Step 2*: Begin at a randomly selected node in the circuit, and include this node in the set of visited nodes. Call this node, node s, and the set of all visited nodes V
*Step 3*: Identify the neighbors of node i: Ni.

 *Note*: If all of the nodes in Ni have been previously visited, quit (end point found). If there are only two nodes in V randomly select one of the nodes in Ni that are not in V , call this node i, add it to V and repeat. If there are more than two nodes in V and the only node in Ni that is not in V is s, then quit (loop of length three or more nodes has been found; repeat from step 1). If there are more than two nodes in V and s is not in Ni, then advanced to a randomly chosen node in Ni that is not in V and repeat this step.

#### **Objectives of GRIP Absorption/island management algorithm**

 -minimize the value-weighted amount of total unserved (shed) non-flexible energy.
 -ensure that we maintain as much battery energy at the end of the time horizon as possible
 -maximize the virtual battery energy at the end of the time horizon.
 -maximize the value-weighted level of customer comfort over the entire time horizon.

#### **Constraints**

The following are the constraints used in the IMO model.

![Absorbance constraints equations](/AB_CONSTRAINTS_EQUATIONS_PART_2.png)

Equation 2.30  ensures that power supply and demand balance over the entire time horizon. Equations 2.31 limit power the output for the solar and non-solar generators.

Equation 2.33 limits batteries power to be within limits and Equation 2.34 limits the setpoint for the virtual battery to be within a reasonable range for the flexible devices. Equation 2.35 limits the load shedding to be within the range of non-flexible load from the baseline timeseries. Equations 2.36 and 2.40 limit the energy state to be within limits for the batteries and virtual battery. Equations 2.37, 2.38, 2.41, and 2.42 model the batteries and virtual batteries energy state over the time horizon.

The output of the optimization is a time-series of setpoint values and the resulting state of-charge of the batteries and virtual battery over the entire time horizon of 24-hours. The figures below shows this output for the optimization of the initial time step of the simulation for both the "fire" represented by *Figure 4* and "ice" represented by *Figure 5* test cases.

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/AB_FIGURE2_6OPTIMAL_OUTPUT_FIRE.png)
##### **Figure 4** *Fire Output*

![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/AB_FIGURE_2_6OPTIMAL_OUTPUT_ICE.png)
##### **Figure 5** *Ice Output*

### **Recovery**

The Extremum Seeking approach has been tested in hardware in the loop experiments and in live field tests. The LBNL team performed multiple validation simulations using the GRIP platform. The LBNL team used the IEEE 37 node test feeder for the simulated distribution network. A multitude of varying objective and control configurations were tested. Simulations show that ES control of distributed resources is a viable method for minimization voltage difference between adjacent and connected buses, or disconnected buses. *The GRIP platform allows easy simulation setup and execution.*

Demonstrated below (*figure 6*) is a simulation that was performed using the GRIP platform. The simulated network was the IEEE 37 node test feeder, and GridLab-D was used to solve power flow.



![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_2_FINAL_REPORT.png)
##### **Figure 6** *Figure 6* above illustrates the topology of the IEEE 37 node test feeder. The objective of the simulation was to minimize the total voltage phasor difference between bus 709 and bus 708 (which were connected during the experiment).


Single phase four quadrant inverters were placed at the following phases and buses: 703-A, 703-B, 703-C, 733-A, 733-B, 733-C (see figure 2). Each inverter was managed by an 2D-ES controller (2D-ESC) with both active power and reactive power probes. All 2D-ESCs utilized a sinusoidal probe for both their active and reactive power probes, all with a unique frequency on the order of 0.1 Hz, for both its active power and reactive power probe. All 2D-ESCs had a constraint on the magnitude of inverter active power of 100 kW, a constraint on the magnitude of inverter reactive power of 100 kVAr, and a constraint on inverter apparent power of 100 kVA. All ESCs had an active power probe magnitude of 10 kW, and a reactive power probe magnitude of 10 kVAr.


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_3_FINAL_REPORT.png)
##### **Figure 7** The above *figure 7* represents the objective function, defined above, over the course of the 10 minute simulation. The objective function is reduced from a value of roughly 210 to roughly 50.



![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_4_FINAL_REPORT.png)
##### **Figure 8** Figure 8 shows the phase a voltage magnitude difference between bus 709 and 708, and the phase a voltage angle difference between bus 709 and 708. The figure demonstrates that the voltage magnitude difference is reduced, as is the voltage angle difference.



![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_5_FINAL_REPORT.png)
##### **Figure 9** *Figure 9* shows the phase b voltage magnitude difference between bus 709 and 708, and the phase b voltage angle difference between bus 709 and 708. The figure demonstrates that the voltage magnitude difference is reduced, as is the voltage angle difference.



![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_6_FINAL_REPORT.png)
##### **Figure 10** *Figure 10* plots the phase c voltage magnitude difference between bus 709 and 708, and the phase c voltage angle difference between bus 709 and 708. The figure demonstrates that the voltage magnitude difference is reduced, as is the voltage angle difference.


![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_7_FINAL_REPORT.png)
##### **Figure 11** *Figure 11* plots the active and reactive power contributions of the inverter on phase a at bus 703. This figure shows the ESC was limited by its maximum apparent power constraint.



![Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-D](/REC_FIGURE_8_FINAL_REPORT.png)
##### **Figure 12** *Figure 12* shown above plots the active and reactive power contributions of the inverter on phase a at bus 733. This figure shows that the ESC was limited by its maximum apparent power constraint.
