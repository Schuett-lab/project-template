# Project Template

This repository contains a template for projects in the lab. Any project is meant to follow this layout and the code part shall be hosted on Github for version control. If parts of this template are a clear misfit with your project, please tell Heiko about it, such that template can be amended to the needs of the lab. 

Below, you find a summary of projects parts and where they are meant to go in this template.

## Parts of a project
The whole project folder should be a folder on your computer that is synchronized to all locations where you need it in such a way that you can share access to other lab members who 
might need it and can allow archiving at the end of the project. 
This synchronization should contain everything that relates to the project: code, data, figures, manuscripts, posters, etc.
The only exception are large datasets (like imagenet, MS CoCo, or the NSD fMRI data). Most DNN training data we use is available on the cluster in a specific folder. Any other big 
data will be organized individually.

### Code
Code should be kept up to date in Github. For any project, there is a repository under the schuett-lab organization and a separate working branch or fork under your own account. Your fork is meant for your day to day work. There you may make any changes, have as many branches you want etc. To commit to the main branch of the schuett-lab organization, we implement code review, i.e. any code that shall go into the main branch has to be seen by at least one other person from the lab who accepts the changes. These reviewed commits to the main branch should happen whenever a step in the code development is complete (like the preprocessing pipeline is implemented, a dataset got newly included, a new model or algorithm was implemented, etc.). Under two circumstances such commits *must* happen: 
- before any submission for publication, all code that is necessary for the paper must be commited to the main branch
- gaps between commits to main shall not be longer than 3 months, Heiko will start bugging you after ~2 months

### Data
There are two types of data that have their own folders in this template: data and derivatives:
- 'data' should be the raw data as you originally saved them in the experiment or downloaded them
- 'derivatives' are any other formats of the data that can be created by your code. Common things to go here are: Preprocessed data and paramter fits of models

Large datasets as used for DNN training should not be copied to the individual project folders. Instead, we want only one copy of these data and your code should have one location where you can set where the data is located. Enforcing a specific relative location for files that cannot be moved easily is not a good idea.

### Models
In general, models should have their separate folders in the code folder and be kept on Github. There are some additional data that may occur in your projects.

- You may have a folder 'models' for the model parameters and checkpoints that occur during training.
- You may have a folder 'results' for simulation results. These would be things that are not based on measured data, but take a long time to compute (otherwise you don't need to save them), for example the model predictions for large datasets or the results of many simulations to test statistical properties of your methods.

Please use one consistent naming scheming across all those folders, i.e. the subfolder in code, models and results should be exactly the same!

### Publication materials
We will prepare publications in other cloud solutions, but the folder should nonetheless contain the final publications that we submit. There should be the folowing other folders:

- 'figures' should contain the figures and their parts
- 'manuscripts' should contain the manuscripts in the form we submit, one folder per submission
- 'presentations' is for posters or talks presented at scientific conferences. Publications in computer science conferences go into 
manuscripts, not here.

These materials will be archived after completion of the project, but will not be published.

## Files in main folder
For orientation there are a couple of files you should keep up to date in the main folder:
- 'requirements.txt' should contain the machine readable description of the dependencies of your code as for pip install . in python. For other languages there should be a 
corresponding file even if no automated way of installing the dependencies or standard format for them is available. 
- 'data_requirements.md' should be a human readable description which files or folder with what content outside the folder are necessary if any. This is the place to describe which 
large data you used and where to set the path to them.
- 'pyproject.toml' and 'setup.py': For python projects please set up these two files as described [here](https://setuptools.pypa.io/en/latest/userguide/pyproject_config.html). This 
will ensure that your project can be installed using standard python tools which makes your code calleable from all locations and enables things like compiling cython and similar 
things. It will also make all things you list in requirements.txt or the pyproject.toml files available.
