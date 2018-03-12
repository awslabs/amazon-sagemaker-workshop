# Introduction to SageMaker

## Modules

This workshop is divided into multiple modules. Module 1 must be completed first, followed by Module 2.  You can complete the other modules (Modules 3 and 4) in any order.  

1. [**Creating a Notebook Instance**](../NotebookCreation) (Follow the link, then return here.)
2. Video Game Sales Notebook
3. Distributed Training with TensorFlow Notebook
4. Image Classification Notebook 

Be patient as you work your way through the notebook-based modules. After you run a cell in a notebook, it may take several seconds for the code to show results. For the cells that start training jobs, it may take several minutes. In particular, the last two modules have training jobs that may last up to 10 minutes.  

After you have completed the workshop, you can delete all of the resources that were created by following the Cleanup Guide provided with this lab guide. 

## Module 2:  Video Game Sales Notebook

In this module, we'll work our way through an example Jupyter notebook that demonstrates how to use an Amazon-provided algorithm in SageMaker. More specifically, we'll use SageMaker's version of XGBoost, a popular and efficient open-source implementation of the gradient boosted trees algorithm. Gradient boosting is a supervised learning algorithm that attempts to predict a target variable by combining the estimates of a set of simpler, weaker models. XGBoost has done remarkably well in machine learning competitions because it robustly handles a wide variety of data types, relationships, and distributions. It often is a useful, go-to algorithm in working with structured data, such as data that might be found in relational databases and flat files. 

To begin, follow these steps:

1. Download this repository to your computer by clicking the green **Clone or download**  button from the upper right of this page, then **Download ZIP**.
2. In your notebook instance, click the **New** button on the right and select **Folder**.  
3. Click the checkbox next to your new folder, click the **Rename** button above in the menu bar, and give the folder a name such as 'video-game-sales'.
4. Click the folder to enter it.
5. To upload the notebook, click the **Upload** button on the right. Then in the file selection popup, select the file 'video-game-sales-xgboost.ipynb' from the notebooks subdirectory in the folder on your computer where you downloaded this GitHub repository. Click the blue **Upload** button that appears to the right of the notebook's file name.
6. You are now ready to begin the notebook:  click the notebook's file name to open it.
7. In the ```bucket = '<your_s3_bucket_name_here>'``` code line, paste the name of the S3 bucket you created in Module 1 to replace ```<your_s3_bucket_name_here>```.  The code line should now read similar to ```bucket = 'smworkshop-john-smith'```.  Do NOT paste the entire path (s3://.......), just the bucket name.  
8. If you are familiar with Jupyter notebooks, you can skip this step.  Otherwise, please expand the instructions below.

<details>
<summary><strong>Jupyter notebook instructions (expand for details)</strong></summary><p>

1. Jupyter notebooks tell a story by combining explanatory text and code. There are two types of "cells" in a notebook:  code cells, and "markdown" cells with explanatory text.  

1. You will be running the code cells.  These are distinguished by having "In" next to them in the left margin next to the cell, and a greyish background.  Markdown cells lack "In" and have a white background.

1. To run a code cell, simply click in it, then either click the **Run Cell** button in the notebook's toolbar, or use Control+Enter from your computer's keyboard.  

1. It may take a few seconds to a few minutes for a code cell to run.  Please run each code cell in order, and only once, to avoid repeated operations.  For example, running the same training job cell twice might create two training jobs, possibly exceeding your service limits.

</p></details>

<p><strong>NOTE:  training the model for this example typically takes about 5 minutes.</strong></p>


## Module 3:  Distributed Training with TensorFlow Notebook

In this module we will be using images of handwritten digits from the [MNIST Database](http://yann.lecun.com/exdb/mnist/) to demonstrate how to perform distributed training using SageMaker. Using a convolutional neural network model based on the [TensorFlow MNIST Example](https://github.com/tensorflow/models/tree/master/official/mnist), we will demonstrate how to use a Jupyter notebook and the [SageMaker Python SDK](https://github.com/aws/sagemaker-python-sdk) to create your own script to pre-process data, train a model, create a SageMaker hosted endpoint, and make predictions against this endpoint. The model will predict what the handwritten digit is in the image presented for prediction. Besides demonstrating a "bring your own script" for TensorFlow use case, the example also showcases how easy it is to set up a cluster of multiple instances for model training in SageMaker.

1. In your notebook instance, click the **New** button on the right and select **Folder**.
2. Click the checkbox next to your new folder, click the **Rename** button above in the menu bar, and give the folder a name such as 'tensorflow-distributed'.
3. Click the folder to enter it.
4. To upload the notebook, click the **Upload** button on the right. Then in the file selection popup, select the file 'TensorFlow_Distributed_MNIST.ipynb' from the notebooks subdirectory in the folder on your computer where you downloaded this GitHub repository. Click the blue **Upload** button that appears to the right of the notebook's file name.
5. You are now ready to begin the notebook:  click the notebook's file name to open it, then follow the directions in the notebook.

<p><strong>NOTE:  training the model for this example typically takes about 8 minutes.</strong></p>

## Module 4:  Image Classification Notebook

For this module, we'll work with an image classification example notebook. In particular, we'll use the Amazon-provided image classification algorithm, which is a supervised learning algorithm that takes an image as input and classifies it into one of multiple output categories. It uses a convolutional neural network (ResNet) that can be trained from scratch, or trained using transfer learning when a large number of training images are not available. Even if you don't have experience with neural networks or image classification, SageMaker's image classification algorithm makes the technology easy to use, with no need to design and set up your own neural network.  

Follow these steps:

1. In your notebook instance, click the **New** button on the right and select **Folder**.  
2. Click the checkbox next to your new folder, click the **Rename** button above in the menu bar, and give the folder a name such as 'image-classification'.
3. Click the folder to enter it.
4. To upload the notebook, click the **Upload** button on the right. Then in the file selection popup, select the file 'Image-classification-transfer-learning.ipynb' from the notebooks subdirectory in the folder on your computer where you downloaded this GitHub repository. Click the blue **Upload** button that appears to the right of the notebook's file name.
5. You are now ready to begin the notebook:  click the notebook's file name to open it, then follow the directions in the notebook.

<p><strong>NOTE:  training the model for this example typically takes about 10 minutes.</strong> However, keep in mind that this is relatively short because transfer learning is used rather than training from scratch, which could take many hours.</p>


## Cleanup

To avoid charges for endpoints and other resources you might not need after the workshop, please refer to the [**Cleanup Guide**](../CleanupGuide).


