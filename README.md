This doc is WIP:

brew install hugo

hugo server - to start the process


# GRIP-Website - https://grip.energy

This repo uses a static website generator - HUGO (https://gohugo.io/)

## Setting Up locally

Install homebrew if not installed.

```
    brew install hugo
```

## Running locally

Navigate to the root directory of this project

```
    hugo server
```

Go to the suggested localhost address on your terminal
(The changes will be auto updated - no need to run this command after every content change)

## Making changes

All the content changes should be happening in the content folder

### Adding a new publication

    1- Navigate to the desired section under /content/publications
    2- Create a new "<li></li>" the same way as what already exists
    3- Upload the pdf of the publication to the GRIP-portal/papers folder in the SharedDrive (Do the same thing with personal drive if not a part of GISMo team)
    4- Update the sharing options to "Anyone with the link" and make sure they are only a viewer
    5.1 - Copy only the ID (the 25 character code) from the sharable link - which is between "https://drive.google.com/file/d/" and "/view?usp=sharing"
    5.2 - Paste it at the end of this link - "https://drive.google.com/uc?export=view&id=" and replace it with the existing URL in the src field

### Adding a new team member

    1- Navigate to /content/team.html
    2- Use existing links as example and follow steps 3-5.2 under "adding a new publication". (Instead of papers, navigate to GRIP-portal/team)

### Adding a use-case

    1- Create a new file in content/use-cases with .md extension
    2- Use an existing use case as example. (the first 4 lines are required)
    3- Update the title on line 2 and start writing markdown for the remainder of the file

### Changing the home page content

    Update the subtitle under profile-mode in config.yml. (this requires rerunning the 'hugo server' command for local testing)

#### To modify existing use-cases update the markdown within any use-case file

### Modifying the Getting Started Guide

    Update the markdown within content/getting-started-guide

## Deploying

    Auto deploy is setup using Netlify. Changes merged in to the main branch auto update https://grip.energy.

## GitHub Repositories
    This link is the main page for the GRIP energy webpage repositories
    https://github.com/slacgismo/grip-webpage/

    This repository includes GRIP-webpage archetypes
    https://github.com/slacgismo/grip-webpage/tree/main/archetypes/

    This repository for the GRIP-webapge content
    https://github.com/slacgismo/grip-webpage/tree/main/content/

    This repository includes the layouts and partials of the GRIP-webpage
    https://github.com/slacgismo/grip-webpage/tree/main/layouts/partials/

    This repository includes the static for the GRIP webpage 
    https://github.com/slacgismo/grip-webpage/tree/main/static/

    This repository includes the themes/ paperMod for the GRIP webpage
    https://github.com/slacgismo/grip-webpage/tree/main/themes/PaperMod/

    This repository includes deployment page set up
    https://github.com/slacgismo/grip-webpage/blob/main/.gitignore/

    This repository includes step by step setup of GRIP website 
    https://github.com/slacgismo/grip-webpage/blob/main/README.md/

    This repository includes the setup for the analytics page of the GRIP webpage
    https://github.com/slacgismo/grip-webpage/blob/main/config.yml/