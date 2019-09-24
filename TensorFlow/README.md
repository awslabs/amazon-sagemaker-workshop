# TensorFlow in Amazon SageMaker

This workshop demonstrates various aspects of TensorFlow usage in Amazon SageMaker.  We'll examine how TensorFlow can be applied in Amazon SageMaker to a natural language processing use case, a structured data use case, and a computer vision use case.  

Here are some of the key features of Amazon SageMaker relevant to TensorFlow demonstrated in this workshop:

- **Script Mode**, which enables you to use your own model definitions and training scripts similar to those outside Amazon SageMaker, with prebuilt TensorFlow containers.
- **Git integration** for Script Mode, which allows you to specify a training script in a Git repository so your code is version controlled and you don't have to download code locally. 
- **Local Mode Training** for rapid prototyping and to confirm your code is working before moving on to full scale model training.
- **Local Mode Endpoints** to test your models and SageMaker inference code before deploying to production in SageMaker hosted endpoints.
- **Hosted Training** for large scale model training.
- **Distributed Training with Parameter Servers** to perform large scale model training.
- **Distributed Training with Horovod** as an alternative to perform large scale model training using the Ring-AllReduce paradigm.
- **Automatic Model Tuning** to find the best model using automation.
- **Test a model checkpoint locally** after retrieving it from SageMaker/S3 (as an alternative to Local Mode Endpoints).
- **Hosted Endpoints** for real time predictions.
- **Batch Transform Jobs** for asynchronous, large scale batch inference.
- **Elastic Inference** for lower-cost GPU acceleration for real time inference.
- **Inference Pre/Post-Processing Scripts** to transform data before sending it to the SageMaker TensorFlow Serving container for inference.


## Modules

This workshop is divided into multiple modules. After completing **Preliminaries**, complete the module **Creating a Notebook Instance** next.  You can complete the remaining modules in any order, though we strongly recommend completing them in order to see how to build a workflow from relatively simple to more complex. 

- Preliminaries

- Creating a Notebook Instance

- Natural Language Processing Use Case:  Sentiment Analysis 

- Structured Data Use Case:  Boston Housing 

- Computer Vision Use Case:  Image Classification  


## Preliminaries

- Be sure you have completed all of the Prerequisites listed in the [**main README**](../README.md). 

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


## Natural Language Processing Use Case:  Sentiment Analysis  

In this module, we'll use Script Mode with TensorFlow by providing our own Python training script to be used with Amazon SageMaker's prebuilt TensorFlow container.  Please go to the following link for this module:  [**Sentiment Analysis**](../modules/Sentiment_Analysis.md).  Be sure to use the **downloaded** version of the applicable Jupyter notebook from this workshop repository.  

When you're finished, return here to move on to the next module.  


## Structured Data Use Case:  Boston Housing

We'll focus on a more complete workflow in this module.  In particular, we'll use Local Mode training and Local Mode endpoints to test our code, and Automatic Model Tuning to find the best model to predict prices based on the Boston Housing dataset.  Please go to the following link for this module:  [**Boston Housing**](../modules/Boston_Housing.md).  Be sure to use the **downloaded** version of the applicable Jupyter notebook from this workshop repository.  

When you're finished, return here to move on to the next module.  


## Computer Vision Use Case:  Image Classification

This module applies TensorFlow within Amazon SageMaker to an image classification use case.  In particular, we'll see how Amazon SageMaker makes distributed training easy for the parameter server method and Horovod.  We'll also use the pre/post-processing script feature of the Amazon SageMaker TensorFlow Serving container to transform data for inference, without having to build separate containers and infrastructure to do this job.  Please go to the following link for this module:  [**CIFAR-10**](../modules/CIFAR-10.md).  Be sure to use the **downloaded** version of the applicable Jupyter notebook from this workshop repository.  

When you're finished, return here and go on to the Cleanup Guide.  


## Cleanup

To avoid charges for endpoints and other resources you might not need after the workshop, please refer to the [**Cleanup Guide**](../CleanupGuide).


