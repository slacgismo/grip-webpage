# Grid Resilience and Intellegence Platform - Public Website

GRIP is a project led by the Department of Energy’s SLAC National Accelerator Laboratory that combines artificial intelligence with massive amounts of data and industry experience from a dozen U.S. partners to identify places where the electric grid is vulnerable to disruption, reinforce those spots in advance and recover faster when failures do occur.

# GRIP-Website - https://grip.energy

This repo uses a static website generator - Jeykll (https://jekyllrb.com/)

## GitHub Repositories
   This repository includes GRIP-webpage archetypes:
    https://github.com/slacgismo/grip-webpage/tree/main/archetypes/

    This repository for the GRIP-webapge content:
    https://github.com/slacgismo/grip-webpage/tree/main/content/

    This repository includes the layouts and partials of the GRIP-webpage:
    https://github.com/slacgismo/grip-webpage/tree/main/layouts/partials/

    This repository includes the static for the GRIP webpage:
    https://github.com/slacgismo/grip-webpage/tree/main/static/

    This repository includes the themes/ paperMod for the GRIP webpage:
    https://github.com/slacgismo/grip-webpage/tree/main/themes/PaperMod/

    This repository includes deployment page set up:
    https://github.com/slacgismo/grip-webpage/blob/main/.gitignore/

    This repository includes step by step setup of GRIP website:
    https://github.com/slacgismo/grip-webpage/blob/main/README.md/

    This repository includes the setup for the analytics page of the GRIP webpage:
    https://github.com/slacgismo/grip-webpage/blob/main/config.yml/
________

## How To Maintain Website Content

### Deployment

There are several alternatives to building and deploying the site:

1. build the site with [GitHub Arras Energy Public Site]([https://github.com/features/actions](https://github.com/arras-energy/static-website)) to build pages and run actions
to the *basic-site* branch. This is the approach that is currently used. 

2. generate the site locally by opening your code editing software's terminal and run

```sh
bundle exec jekyll serve --livereload
```
and cmd select "server adress:" to veiw the live site while you edit. Then push the resulting
HTML to a Github repository, that GitHub Pages then host;

3. commit and push all changes through GitHub desk top or using the code editing terminal 

For option **2)** simply clone this repository (*master branch*), and then run
`bundle exec jekyll serve` inside the directory. Upload the resulting `_site/` (or `../static-website-pages/`)
contents to your repository (*master branch* if uploading as your personal page
(e.g. username.github.io) 

For option **3)** you will need to set up travis-ci for your personal fork. Briefly all you
need then is to change your details in *[\_config.yml](_config.yml)* so that you can push
to your github repo. You will also need to generate a secure key to add to your
*[.travis.yml](.travis.yml)* (you can find more info on how to do it in that file).
This approach has clear
advantages in that you simply push your file changes to GitHub and all the HTML files
are generated for you and pushed to *gh-pages*. 

### Adding Content Pages

In order to properly generate Content pages you need to create a new file and add a index.md file with the tab *name* as defined in the *[\_config.yml](_config.yml)* file. Make sure to page details to the top. 

```sh
---
layout: page
cover: 'assets/images/close.jpg'
title: Enter your title here
navigation: true
logo: 'assets/images/arras.png'
current: about
---
```

## Run on GitHub
<img width="1428" alt="GitHub Pages" src="https://github.com/arras-energy/static-website/assets/128001866/088211f7-1bed-4bc5-9805-c031a08de475">

You can run GRIP with GitHub Actions using the template https://github.com/gridlabd-tutorials/.new_project. The simulation results are stored in a downloadable file that can accessed from the ```Actions``` tab in your GitHub project. A tutorial for using Arras Energy with GitHub is available at https://github.com/gridlabd-tutorials.

## Run on Docker

To run a GridLAB-D simulation using Docker, follow these steps:

1. Open your terminal or command prompt.

2. Navigate to the directory where your GridLAB-D model file is located.

3. Use the following Docker command to run the simulation:

```sh
docker run -it -v $PWD:/model slacgismo/gridlabd:latest gridlabd -W /model [LOADOPTIONS] [FILENAME.EXT] [RUNOPTIONS]
```

## Run on AWS
1. Sign into your AWS console.
2. Launch an EC2 instance.
3. Search the community AMI for images starting with gridlabd in the us-west-1 (N. California) region.
4. Choose an instance type with sufficient memory, e.g., >4GB.
5. Download and save your keypair.
6. Launch the instance.
7. Connect to the instance.
8. Download your model into the instance, e.g., from GitHub.
9. Run the simulation using the usual command line options.
10. Save the results, e.g., to GitHub.

You can also start the instance from the command line:
```sh
aws ec2 run-instances --image-id AMINAME --count 1 --instance-type INSTANCETYPE --key-name KEYPAIRNAME --security-group-ids SECURITYGROUPID --subnet-id SUBNETID
```

You can search the [AWS AMI Catalog](https://us-west-1.console.aws.amazon.com/ec2/home?AMICatalog%3A=&region=us-west-1#AMICatalog:) for Community AMIs matching "Arras Energy HiPAS GridLAB-D" in the us-west-1 region. The version number will be included in the name.

## Download on Mac, Windows WSL, or Ubuntu Linux
```sh
curl -sL https://install.gridlabd.us/install.sh | [sudo] sh
```

## Build your own
```sh
git clone https://source.gridlabd.us/ [-b BRANCH] gridlabd
cd gridlabd
./setup.sh --local
./build.sh --system --validate
```

## Issues and contributing

This website refers to all installations and tutorials on Arras Energy's offical GitHub page. If you run into any problems please refer to [GRIP Energy GitHub](https://github.com/slacgismo/grip-webpage) for more information.
Feel free pull-request your patches and fixes.
