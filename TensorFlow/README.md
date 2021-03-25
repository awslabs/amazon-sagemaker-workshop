# TensorFlow in Amazon SageMaker

This workshop demonstrates various aspects of how to work with custom TensorFlow models in Amazon SageMaker.  We'll examine how TensorFlow can be applied in  SageMaker to a natural language processing use case, a structured data use case, and a computer vision use case.  

Here are some of the key features of SageMaker demonstrated in this workshop:

- **Data Processing**
  - **SageMaker Processing** for data preprocessing tasks within SageMaker.

- **Prototyping and Working with Code**
  - **Script Mode**, which enables you to use your own custom model definitions and training scripts similar to those outside Amazon SageMaker, with prebuilt TensorFlow containers.
  - **Git integration** for Script Mode, which allows you to specify a training script in a Git repository so your code is version controlled and you don't have to download code locally. 
  - **Local Mode Training** for rapid prototyping and to confirm your code is working before moving on to full scale model training.
  - **Local Mode Endpoints** to test your models and inference code before deploying with TensorFlow Serving in SageMaker hosted endpoints for production.

- **Training and Tuning Models**
  - **Hosted Training** for large scale model training.
  - **Automatic Model Tuning** to find the best model hyperparameters using automation.
  - **Distributed Training with TensorFlow's native MirroredStrategy** to perform training with multiple GPUs on a *single* instance.
  - **Distributed Training on a SageMaker-managed cluster** of *multiple* instances using either the SageMaker Distributed Training feature, or parameters servers and Horovod.

- **Inference**
  - **Hosted Endpoints** for real time predictions with TensorFlow Serving.
  - **Batch Transform Jobs** for asynchronous, large scale batch inference.
  - **Model evaluation or batch inference** with SageMaker Processing.

- **Workflow Automation**
  - **SageMaker Pipelines** for creating an end-to-end automated pipeline from data preprocessing to model training to hosted model deployment.  


## Modules

This workshop is divided into multiple modules that should be completed in order. After **Preliminaries**, complete the module **Creating a Notebook Environment**.  The next two modules, NLP and Structured Data, should be completed in order to show how to build a workflow from relatively simple to more complex. 

- Preliminaries

- Creating a Notebook Environment

- Natural Language Processing (NLP) Use Case:  Sentiment Analysis 

- Structured Data Use Case:  End-to-End Workflow for Boston Housing Price Predictions 

- Computer Vision Use Case:  Image Classification  


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


## Natural Language Processing Use Case:  Sentiment Analysis  

In this module, we'll train a custom sentiment analysis model by providing our own Python training script for use with Amazon SageMaker's prebuilt TensorFlow 2 container.  Assuming you have cloned this repository into your notebook environment (which you should do if you haven't), open the `notebooks` directory of the repository and click on the `sentiment-analysis.ipynb` notebook to open it.  

When you're finished, return here to move on to the next module.  


## Structured Data Use Case:  End-to-End Workflow for Boston Housing Price Predictions

We'll focus on a relatively complete TensorFlow 2 workflow in this module to predict prices based on the Boston Housing dataset.  In particular, we'll preprocess data with SageMaker Processing, prototype training and inference code with Local Mode, use Automatic Model Tuning, deploy the tuned model to a real time endpoint, and examine how SageMaker Pipelines can automate setting up this workflow for a production environment.  Assuming you have cloned this repository into your notebook environment (which you should do if you haven't), open the `notebooks` directory of the repository and click on the `tf-2-workflow-smpipelines.ipynb` notebook to open it.  

When you're finished, return here to move on to the next module.  


## Computer Vision Use Case:  Image Classification

This module applies TensorFlow within Amazon SageMaker to an image classification use case.  Currently we recommend using the example [TensorFlow2 and SMDataParallel](https://github.com/aws/amazon-sagemaker-examples/tree/master/training/distributed_training/tensorflow/data_parallel/mnist).  This example applies the SageMaker Distributed Training feature with data parallelism to train a model on multiple instances.  (Model parallelism is another possibility.)  

Alternatively, there is a TensorFlow 1.x example for the parameter server method and Horovod.  This example also uses the pre/post-processing script feature of the SageMaker TensorFlow Serving container to transform data for inference, without having to build separate containers and infrastructure to do this job.  Assuming you have cloned this repository into your notebook environment (which you should do if you haven't), open the `notebooks` directory of the repository and click on the `tf-distributed-training.ipynb` notebook to open it.  
When you're finished, return here and go on to the Cleanup Guide.  


## Cleanup

To avoid charges for endpoints and other resources you might not need after the workshop, please refer to the [**Cleanup Guide**](../CleanupGuide).


