# Introduction to SageMaker

In this workshop, we'll work though several examples that demonstrate Amazon SageMaker's core components including SageMaker Studio (or notebook instances), hosted training, and hosted model endpoints.  Examples are divided into modules.  The examples show how Amazon SageMaker can be applied in three of the common categories of machine learning:  working with structured data, computer vision, and natural language processing.  

We'll make use of some of Amazon SageMaker's built-in algorithms, specifically an AWS-optimized version of XGBoost and a deep learning-based image classification algorithm.  Built-in algorithms enable you to avoid spending time against algorithm/neural net design, provide conveniences such as reduced need for model tuning, and are meant to handle the scalability and reliability issues that arise when working with large datasets.  As a contrast, in one module we'll use a script defining our own custom deep learning model instead of a built-in algorithm.  Whether you define your own custom models or use built-in algorithms, all of Amazon SageMaker's features may be used in a similar way.  

To summarize, here are some of the key components and features of Amazon SageMaker demonstrated in this workshop:

- Using **SageMaker Studio** (or Notebook Instances) for Exploratory Data Analysis and prototyping.
- **Choosing different instance types** for different use cases (CPU vs. GPU, model training vs. deployment, etc.).
- **Hosted Training** for large scale model training.
- **Built-in algorithms** designed for web scale and rapid prototyping of data science projects without the need to write a lot of code.
- **Script Mode**, which enables you to use your own custom model definitions and scripts similar to those outside SageMaker, with prebuilt machine learning containers.
- **Hosted Endpoints** for real-time predictions.
- **Batch Transform** for asynchronous, large scale batch inference.



## Modules

This workshop is divided into multiple modules. After completing **Preliminaries**, complete the module **Creating a Notebook Environment** next.  You can complete the remaining modules in any order, EXCEPT the Videogame Sales module must be completed before the Extra Credit module. 

- Preliminaries

- Creating a Notebook Environment

- Structured Data Use Case:  Videogame Sales 

- Computer Vision Use Case:  Image Classification  

- Natural Language Processing Use Case:  Sentiment Analysis 

- Extra Credit:  Videogame Sales Using Scripts, the CLI and Console


## Preliminaries

- Be sure you have completed all of the Prerequisites listed in the [**main README**](../README.md). 

- If you are new to using Jupyter notebooks, read the next section, otherwise you may now skip ahead to the next module.

### Jupyter Notebooks:  A Brief Overview

Jupyter is an open-source web application that allows you to create and share documents that contain live code, equations, visualizations and narrative text. Uses include: data cleaning and transformation, numerical simulation, statistical modeling, data visualization, machine learning, and much more. With respect to code, it can be thought of as a web-based IDE that executes code on the server it is running on instead of locally. 

There are two main types of "cells" in a notebook:  code cells, and "markdown" cells with explanatory text. You will be running the code cells.  These are distinguished by having "In" next to them in the left margin next to the cell, and a greyish background.  Markdown cells lack "In" and have a white background. In the screenshot below, the upper cell is a markdown cell, while the lower cell is a code cell:

![Cells](../images/cells.png)

To run a code cell, simply click in it, then either click the **Run Cell** button in the notebook's toolbar, or use Control+Enter from your computer's keyboard. It may take a few seconds to a few minutes for a code cell to run. You can determine whether a cell is running by examining the `In[]:` indicator in the left margin next to each cell:  a cell will show `In [*]:` when running, and `In [a number]:` when complete.

Please run each code cell in order, and **only once**, to avoid repeated operations.  For example, running the same training job cell twice might create two training jobs, possibly exceeding your service limits.


## Creating a Notebook Environment

SageMaker provides hosted Jupyter notebooks that require no setup, so you can begin processing your training data sets immediately. With a few clicks in the SageMaker console, you can create a fully managed notebook environment, pre-loaded with useful libraries for machine learning. You need only add your data.  You have two different options for this workshop.  Follow the choice specified by your workshop instructor if you're in a live workshop, or make your own choice otherwise:

- **SageMaker Studio**:  An IDE for machine learning. To create a SageMaker Studio domain for this workshop, follow the instructions at [**Creating an Amazon SageMaker Studio domain**](../StudioCreation), then return here to continue with the next module of the workshop.

- **SageMaker Notebook Instance**:  A managed instance with preinstalled data science tools (though not as fully managed as SageMaker Studio).  To create a SageMaker notebook instance for this workshop, follow the instructions at [**Creating a Notebook Instance**](../NotebookCreation), then return here to continue with the next module of the workshop.


## Structured Data Use Case:  Videogame Sales

In this module, we'll use Amazon SageMaker's built-in version of XGBoost to make predictions based on structured data related to the videogame industry.  Assuming you have cloned this repository into your notebook environment (which you should do if you haven't), open the `notebooks` directory of the repository and click on the `videogame-sales.ipynb` notebook to open it.   Make sure you are using the `Python 3 (Data Science)` kernel if you're using SageMaker Studio.  

When you're finished, return here to move on to the next module.  


## Computer Vision Use Case:  Image Classification

This module uses Amazon SageMaker's built-in Image Classification algorithm.  Assuming you have cloned this repository into your notebook environment (which you should do if you haven't), open the `notebooks` directory of the repository and click on the `Image-classification-transfer-learning.ipynb` notebook to open it.   Make sure you are using the `Python 3 (Data Science)` kernel if you're using SageMaker Studio.  

When you're finished, return here to move on to the next module.  


## Natural Language Processing Use Case:  Sentiment Analysis  

In contrast to the previous modules, which used some of Amazon SageMaker's built-in algorithms, in this module we'll use a deep learning framework within Amazon SageMaker with our own script defining a custom model.  Assuming you have cloned this repository into your notebook environment (which you should do if you haven't), open the `notebooks` directory of the repository and click on the `sentiment-analysis.ipynb` notebook to open it.  Make sure you are using the `Python 3 (Data Science)` kernel if you're using SageMaker Studio.

When you're finished, return here and go on to the Extra Credit module or Cleanup Guide.  


## Extra Credit:  Videogame Sales Using Scripts, the CLI and Console 

The previous modules all use Jupyter notebooks to demonstrate the use of hosted training and hosted model endpoints in Amazon SageMaker.  However, in a typical machine learning pipeline, scripts are used to launch training jobs and deploy models, not notebooks.  Also, it is convenient to use the console for these tasks on an ad hoc basis without having to open notebooks or use scripts.

In this extra credit module, you will revisit the Videogame Sales example, but use Bash scripts to launch a training job and the Amazon SageMaker console to deploy the trained model.  Here are the steps you will need to take before beginning this module:

- Be sure you have completed the first module, **Structured Data Use Case:  Videogame Sales**.
- Copy the name of the default bucket created in the first cell of the Videogame Sales notebook from the first module.  It should look like:  `sagemaker-<region>-<your_account_id>`.
- Go to the following link and start at **Step 8 (Training Job)**:  [**Videogame Sales with the CLI and Console**](../modules/Video_Game_Sales_CLI_Console.md).  When the instructions ask for a bucket name, **USE THE BUCKET NAME YOU JUST COPIED.**

## Cleanup

If you are using your own AWS account rather than one provided at an AWS-run event:  To avoid charges for endpoints and other resources you might not need after the workshop, please refer to the [**Cleanup Guide**](../CleanupGuide).


