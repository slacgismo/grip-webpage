---
layout: page
cover: 'assets/images/lightning2.jpg'
navigation: True
title:  "OpenFIDO | GRIP"
date:   2023-07-20 11:59:00 -0700
logo: 'assets/images/griplogo.svg'
current: about
---
# Learn How To Use OpenFIDO

[Getting Started:](http://app.openfido.org){:target="_blank"} 
There are several options to help new users starting out with OpenFIDO, which is accessible through several distinct methods, or developers looking to help contribute to the project.


	
## Sign up to shared app
You can email the [support@openfido.org](mailto:support@openfido.org) to request to utilize the online application's resources. Once your request to use the application is approved, you will have access to all publicly available repositories that can be automatically searched in this organization, or you can manually designate your own repositories to run.

## Host Locally
You can follow the instructions on the [OpenFIDO App Service](https://github.com/openfido/openfido-app-service){:target="_blank"} page or the [OpenFIDO Command Line Interface](https://github.com/openfido/cli){:target="_blank"} to set up locally, and run OpenFIDO to your prefererred method. 

## Deploy to AWS
You can use this code as a base to deploy your own OpenFIDO AWS servers. While the majority of the terraform modules used to deploy this are available in the centralized [OpenFIDO](https://github.com/openfido/openfido){:target="_blank"} repository, you will need to provide your own code for the cloudfront, rds, ecs, and ses terraform modules, as those are proprietary and licensed to us, and therefore unavailable for use. 

## Simulation Set-up

Navigate to the sign-in page and use your credentials to gain access.

<img src="{{ site.baseurl }}assets/images/OPENFIDO1.png" alt="openfido1" style="max-width: 480px;">

Add a new pipeline. 

<img src="{{ site.baseurl }}assets/images/OPENFIDO2.png" alt="openfido2" style="max-width: 550px;">

Configure the pipeline for a Resilience use-case using the dropdown menu. 

<img src="{{ site.baseurl }}assets/images/OPENFIDO3.png" alt="openfido3" style="max-width: 550px;">

## Learn More
Check out the [Publications](https://arras-energy.github.io/static-website/literature/) for in-depth literature and news articles on GRIP. Learn about the sucess stories of GRIP's implentation for [Use-Cases](https://arras-energy.github.io/static-website/use-cases/). File all bugs/feature requests at [GRIP's GitHub repo](https://github.com/arras-energy).

[Tutorials]:  https://arras-energy.github.io/static-website/tutorials/
[Reports]:   https://arras-energy.github.io/static-website/literature/ 
[Use-Cases]:  https://arras-energy.github.io/static-website/use-cases/ 
[GRIP's GitHub repo]: https://github.com/arras-energy
