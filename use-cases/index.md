---
layout: page
cover: 'assets/images/talking.jpg'
navigation: True
title:  "Use Cases | GRIP"
date:   2023-07-20 11:59:00 -0700
logo: 'assets/images/griplogo.svg'
current: about
---

# Grid Resilence In Action
The goal of GRIP is to assist distribution utilities in responding to grid events by:

- Anticipating grid events using machine learning and artificial intelligence techniques with diverse data sources.
- Absorbing grid events by employing validated control strategies for distributed energy resources; and
- Reducing recovery time by managing distributed energy resources in the case of limited communications.

# Anticipation
Watch our video Tutorial for a Pole Analysis and Vegetation Case!
<iframe width="560" height="315" src="https://www.youtube.com/embed/RRb0aqSEcyE?si=Sxe3AhaDIwDF1jkI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

# Absorption
### GRIP Absorption Objectives

1. Minimize the value-weighted amount of unserved load.

2. Maintain as much reserve as possible to account for future load increases.

3. Maximize the batteries state of-charge at the final time step

4. Minimize the number of switching events and the total number of loads that are “on” for reserves accounting.

The work described here was led by Packetized Energy and is one component of a research and development initiative led by the SLAC National Accelerator Laboratory known as GRIP: The Grid Resilience and Intelligence Platform.

The GRIP Absorption platform allows electric utilities to better understand how they can transition to a system in which distribution circuits can continue to serve load, even after either the bulk grid or portions of a distribution circuit (or both) are damaged by extreme events. The aim of Absorption is to allow distribution networks to “absorb" disturbances through automatic reconfiguration of feeders into microgrids(each operates with local resources to serve as much load as possible). This can be achieved through the use of two forms of technology such as Virtual Islanding technology and Packetized Energy Management. Virtual Islanding technology enables a distribution circuit to be automatically reconfigured into self-managing microgrids. Packetized Energy Management has been adapted to the specific problem of using distributed energy resources within the automatically formed islands to maintain the balance between supply and demand, while serving as much load as possible.

### Real-world use-case scenarios using Virtual Islanding Model:
Validation of the Virtual Islanding algorithms were used where two different test systems were developed: a small 11-node distribution system that was used for preliminary validation and a larger test case based on real data from our utility partner, Vermont Electric Coop. The 11-node test case includes two substation nodes and three feeders, each of which includes both distributed Solar PV generation and grid-scale storage. In addition, it is assumed that there are many ‘packetized’ water heaters and HVAC systems that can contribute to network balancing. For the purpose of validation, two case illustrative resilience scenarios were developed:(Case 1: Fire) to represent fire damage to a distribution network and (Case 2:Ice) to represent ice damage.

### Use-case: Case 1 (Fire)

While using the Virtual Islanding model, weather data was used from Los Angeles, CA and modeled the date October 15, 2020. This use-case involves wildfires taking out the bulk grid as well as the “supernode” in the distribution circuit where a solar plant is located. Figures 1(a),2(b), and 3(c) represent the fault locations, the results during the “baseline”, where the absorption module is turned off, and the results when absorption is turned on. The resulting virtual island is shown by the dashed line in Figure 3(c).

<img src="{{ site.baseurl }}assets/images/ab.png" alt="linux" style="max-width: 550px;">

*Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-DFigure 1(a): Fire Test Case, Figure 1(b): Fire Baseline Results, Figure 1(c): Fire Absorption Results*

### Use-case: Case 2 (Ice)

While using the Virtual Islanding model, weather data was used from Burling ton, VT and modeled the date January 30, 2020. This use-case involves an ice storm that takes out three nodes “supernodes" in the distribution circuit, one with a utility scale battery and one with a solar plant. Figures 2(d),2(e), and 2(f) illustrate the fault locations, the results during the “baseline”, where the absorption module is turned off, and the results when absorption is turned on. The resulting virtual islands are shown by the dashed line in Figure 2(f),however, the one in blue is an isolated island that is not supported by the bulk grid.

<img src="{{ site.baseurl }}assets/images/ab2.png" alt="linux" style="max-width: 550px;">

*Figure 1-Hinesburg circuit plotted with edge width relative to GridLab-DFigure 2(d): Ice Test Case, Figure 2(e): Ice Baseline Results, Figure 2(f): Ice Absorption Results*

### Virtual Island Management Optimization

The two factors that are needed to manage the distributed resources within those islands are:

1. ‘Island Management Optimization’ (IMO) tool that centrally optimizes the assets within the island, including the aggregated group of smaller Packetized DERs.

2. A Packetized Virtual Battery server that manages the smaller DERs as a group based on signals from the IMO.

The Island Management Optimization takes information about the current state of larger DERs (or aggregated Packetized Virtual Batteries) in an islanded subsection of the distribution circuit, or micro-grid and the “baseline” or business-as-usual time-series data for that island, and returns the setpoints for the DERs or DER groups for the next time step. This controller is formulated as a receding horizon control (RHC) optimization problem of which is described in greater detail in the Publications section titled Absorbance Final Report.

# Recovery
Goal of the Recovery Phase and GRIP: leverage distributed energy resources (DER) to facilitate faster and safer electricity distribution network reconfiguration and recovery after a catastrophic network event.

### The Recovery use-case characteristics
1. Increase the speed and safety of grid Recovery
2. Used to reconfigure portions of the grid by opening/closing switches

### Current strategies
1. Use of utility crews to be deployed with mobile generation to facilitate switching
2. Minimizing power surges
3. Arcing when opening/closing switches

In order to prevent large power surges, acing, and equipment damage during switching actions, DER will be employed to minimize the voltage difference across the ends of a switch.

**Cool Features of DER**
-reduce the need for manned utility crews -DER will be managed by a model-free online optimization algorithm-ES

**Description of the process/scenario:**
Extremum Seeking (ES) is a model-free optimization and control approach that can be utilized online or offline. ES approximates gradient descent (in single and multiple dimensions). Through disturbance of system input (output of the ES), the ES algorithm estimates the gradient of an unknown objective function with respect to its control setpoint(s). The Extremum Seeking approach has been tested in hardware in the loop experiments and in live field tests.


## Learn More
Check out the [Tutorials](https://arras-energy.github.io/static-website/tutorials/) for more quick access to learning materials. Read into in-depth literature and news articles at [Reports](https://arras-energy.github.io/static-website/literature/). File all bugs/feature requests at [Arras Energy's GitHub repo](https://github.com/arras-energy).

[Tutorials]:  https://arras-energy.github.io/static-website/tutorials/
[Reports]:   https://arras-energy.github.io/static-website/literature/ 
[Use-Cases]:  https://arras-energy.github.io/static-website/use-cases/ 
[Arras Energy's GitHub repo]: https://github.com/arras-energy