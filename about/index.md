---
layout: page
cover: 'assets/images/lines.jpg'
title: About | GRIP
navigation: true
logo: 'assets/images/arras.png'
current: about
---


# Combating Cilmate Change with Electrical Grid Resilience

GRIP (Grid Resilience and Intellegence Platform) is a cutting-edge software platform designed to help electric grid operators anticipate, mitigate against, and recover from the effects of extreme weather events.

By combining state-of-the-art agent-based grid modeling tools with grid resilience metrics, GRIP can quantify the state of the grid assets before extreme events, and provide grid operators with actionable insights, such as staging maintenance crew locations, proactive pole hardening or grid topology reconfiguration, to help minimize equipment damage and revenue loss due to power outages.

## Background

GRIP is a project led by the Department of Energy’s SLAC National Accelerator Laboratory that combines artificial intelligence with massive amounts of data and industry experience from a dozen U.S. partners to identify places where the electric grid is vulnerable to disruption, reinforce those spots in advance and recover faster when failures do occur.

<img src="{{ site.baseurl }}assets/images/fire.jpg" alt="linux" style="max-width: 520px;">

The goal of GRIP is to assist distribution utilities in responding to grid events by:

- Anticipating grid events using machine learning and artificial intelligence techniques with diverse data sources.
- Absorbing grid events by employing validated control strategies for distributed energy resources; and
- Reducing recovery time by managing distributed energy resources in the case of limited communications.

With GRIP, electrical utility operators can reduce operating costs by optimizing grid hardening costs and lowering liability costs and shareholder exposure. These grid operator benefits will ultimately lead to lower electricity rates for customers. 

## Customer Need

Increasingly frequent severe weather events cost grid operators billions of dollars per year in repair cost. In 2022, $12.4 billion in weather related utility debt was issued in the U.S., which has led to dramatic increase in prices of electricity across several states. In the state of Louisiana alone, severe storms caused an estimated $4.4 billion in grid damage in 2020 and 2021. In response to this growing risk, grid operators are spending billions of dollars annually to harden their infrastructure against harm. 

<img src="{{ site.baseurl }}assets/images/2workers.jpg" alt="linux" style="max-width: 500px;">

Without effective tools to guide these investments, their effectiveness is limited.  Utilities are plagued by department data silos, leaving them ill-equipped to focus their grid hardening investments where it will do the most good. In addition, these silos result in an inability to quantify the indirect costs associated with large scale weather events, such as accident liability costs. Without an accurate view into these costs, grid operators struggle to justify long term investments disassociated from short-term rate design cycle. 

## Approach

GRIP uses telemetry data to identify infrastructure most at risk from severe weather. One of the key strengths of GRIP is its threat-agnostic grid modeling capabilities. Regardless of the type of extreme weather event, if telemetry data is available regarding the failed asset, GRIP's system modeling capabilities can provide actionable insights to the grid operator. By taking an overall system perspective, GRIP is unique in its ability to coordinate heterogeneous datasets and derive numerous features to enable a proactive response to extreme weather. GRIP integrates disparate sources of data that don't usually get analyzed in the same context, while also providing an alternative source of data for the information that may not be available internally. For example, prior to an event, GRIP can use telemetry data to identify portions of the grid that are most likely to experience asset failure due to extreme wind or vegetation strike or identify wildland areas at risk of wildfire from close grid interface . Armed with this information, grid operators can deploy field resources in a timely manner to minimize equipment damage or loss of revenue due to power outages.

Prior to an extreme weather event, GRIP can generate scenarios to minimize customer impact. For example, if dry conditions and extreme winds are forecast for a particular section of the distribution system, GRIP can run a topology optimization algorithm and illustrate how to operate the system with two main objectives: minimizing the risk of wildfire and minimizing the magnitude and duration of power outages associated with that section of the grid. The algorithm prioritizes electrical resources based on wildfire risk, availability of DERs, and neighborhood census data to account for equity gaps. 

Prior to an extreme weather event, GRIP can generate scenarios to minimize customer impact. For example, if dry conditions and extreme winds are forecast for a particular section of the distribution system, GRIP can run a topology optimization algorithm and illustrate how to operate the system with two main objectives: minimizing the risk of wildfire and minimizing the magnitude and duration of power outages associated with that section of the grid. The algorithm prioritizes electrical resources based on wildfire risk, availability of DERs, and neighborhood census data to account for equity gaps. 

## Benefits

GRIP can unlock several benefits, including:

Improved Resilience: GRIP can help to improve the resilience of the energy grid by providing early warning of potential disruptions and enabling a rapid response to these disruptions. Given limited resources, GRIP aids in determining the grid asset hardening prioritization given grid topology, local generation, types of consumers and other relevant data. This can help reduce the impact of disruptions and minimize downtime, in turn reducing liability costs due to negligence, and reduce grid hardening costs.

Revenue Impact: GRIP can evaluate the reliability and resilience performance of the electrical grid. GRIP can provide real-time monitoring of grid performance, predictive maintenance, and the ability to quickly respond to disruptions. This can help to reduce downtime and improve the overall efficiency of the energy system, helping to attract new customers and increase revenue by unlocking new revenue streams. 

<img src="{{ site.baseurl }}assets/images/dirt.jpg" alt="linux" style="max-width: 520px;">

Equity and diversity: GRIP is designed to quantify the impact of devastating events on the entire electricity distribution system. By considering the census data, system topology redundancy, local generation and resiliency-enabling technology availability, GRIP can aid utility operators to correctly allocate limited energy resources while best supporting  disadvantaged communities.

## Competitive Advantage

Several commercially available products on the market provide tailored solutions to either address system design or provide hosting platforms for utility data. Utilities also depend on in-house software tools to help manage operations. This diversity of tools results in uncoordinated intra department data sharing, gaps in analysis and overall operational inefficiency. As a result, GRIP provides more features for the same price as the competition.

## Next Steps

For GRIP to reach its scalable commercial potential, the platform requires additional utility deployments to generate the key performance metrics data from a real operational system. To address this challenge, we have secured additional funding to integrate the GRIP with a transactive utility operation system deployed at New Hampshire Electric Cooperative and plan to deploy it in the utilities under the Efficiency Maine Trust’s jurisdiction. We will continue working with SCE and other utilities to develop additional use-cases. Furthermore, we will seek out additional partners to deploy and utilize GRIP in other geographical locations. 



## Learn More
Check out the [Tutorials](https://arras-energy.github.io/static-website/tutorials/) for more quick access to learning materials. Learn about the sucess stories of Arras Energy's implentation for [Use-Cases](https://arras-energy.github.io/static-website/use-cases/). Read into in-depth literature and news articles at [Reports](https://arras-energy.github.io/static-website/literature/). 

## Authors
Chassin, David P., Alyona I. Teyber, Elizabeth Buechler, Duncan Ragsdale, Matthew Tisdale. 2023. HiPAS GridLAB-D: High-Performance Agent-based Simulation with GridLAB-D.
California Energy Commission. Publication Number: CEC-500-202X-XXX.

[Tutorials]:  https://arras-energy.github.io/static-website/tutorials/
[Reports]:   https://arras-energy.github.io/static-website/literature/ 
[Use-Cases]:  https://arras-energy.github.io/static-website/use-cases/  
[Arras Energy's GitHub repo]: https://github.com/arras-energy

