# Simplify Workflows with Scripts, the CLI and Console 

## Modules

This workshop is divided into multiple modules. After completing **Preliminaries**, complete the module **Creating a Notebook Instance** next.  You can complete the remaining modules in any order. 

- Preliminaries

- Creating a Notebook Instance

- Videogame Sales with the CLI and Console

- Distributed Training with Built-in Algorithms, the CLI and Console 


## Preliminaries

- Be sure you have completed all of the Prerequisites listed in the [**main README**](../README.md).  This workshop makes use of the AWS CLI and requires the use of a Bash environment for scripting. AWS Cloud9 is used to run the CLI and scripts; if you haven't done so already, please complete the [**Cloud9 Setup**](../Cloud9).

- **DOWNLOAD THIS REPOSITORY TO YOUR COMPUTER**. To do so:
  - Return to the home page of this GitHub repository or open it in another tab;
  - Click the green **Clone or download** button from the upper right of the main page of the repository, then **Download ZIP**.
  - Use the downloaded notebooks in the notebooks directory rather than other versions you might find inside your notebook instance or elsewhere; the downloaded versions are modified for use in workshops.  

If you are new to using Jupyter notebooks, read the next section, otherwise you may now skip ahead to the next module.

### Jupyter Notebooks:  A Brief Overview

Jupyter is an open-source web application that allows you to create and share documents that contain live code, equations, visualizations and narrative text. Uses include: data cleaning and transformation, numerical simulation, statistical modeling, data visualization, machine learning, and much more. With respect to code, it can be thought of as a web-based IDE that executes code on the server it is running on instead of locally. 

There are two main types of "cells" in a notebook:  code cells, and "markdown" cells with explanatory text. You will be running the code cells.  These are distinguished by having "In" next to them in the left margin next to the cell, and a greyish background.  Markdown cells lack "In" and have a white background. In the screenshot below, the upper cell is a markdown cell, while the lower cell is a code cell:

![Cells](../images/cells.png)

To run a code cell, simply click in it, then either click the **Run Cell** button in the notebook's toolbar, or use Control+Enter from your computer's keyboard. It may take a few seconds to a few minutes for a code cell to run. You can determine whether a cell is running by examining the `In[]:` indicator in the left margin next to each cell:  a cell will show `In [*]:` when running, and `In [a number]:` when complete.

Please run each code cell in order, and **only once**, to avoid repeated operations.  For example, running the same training job cell twice might create two training jobs, possibly exceeding your service limits.


## Creating a Notebook Instance

SageMaker provides hosted Jupyter notebooks that require no setup, so you can begin processing your training data sets immediately. With a few clicks in the SageMaker console, you can create a fully managed notebook instance, pre-loaded with useful libraries for machine learning. You need only add your data.

To create a SageMaker notebook instance for this workshop, follow the instructions at [**Creating a Notebook Instance**](../NotebookCreation), then return here to continue with the next module of the workshop.


## Videogame Sales with the CLI and Console

Please go to the following link for this module:  [**Videogame Sales with the CLI and Console**](../modules/Video_Game_Sales_CLI_Console.md).  Be sure to use the **downloaded** version of the applicable Jupyter notebook from this workshop repository.  

When you're finished, return here to move on to the next module.  


## Distributed Training with Built-in Algorithms, the CLI and Console 
 
Please go to the following link for this module:  [**Distributed Training with Built-in Algorithms, the CLI and Console**](../modules/Distributed_Training_CLI_Console.md).  Be sure to use the **downloaded** version of the applicable Jupyter notebook from this workshop repository.  

When you're finished, return here and go on to the Cleanup Guide.  


## Cleanup

To avoid charges for endpoints and other resources you might not need after the workshop, please refer to the [**Cleanup Guide**](../CleanupGuide).








