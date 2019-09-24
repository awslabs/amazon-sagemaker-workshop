## CIFAR-10 


In this module, we'll perform image classification on the well-known CIFAR-10 dataset.  We'll focus on distributed training using the well-known parameter servers method as well as Horovod, which uses the Ring-AllReduce paradigm rather than parameter servers to share gradients in a cluster of machines.  Additionally, we'll look at how to use Amazon Elastic Inference for lower cost real time inference, and how to use inference pre/post-processing scripts with Amazon SageMaker's TensorFlow Serving container to transform data before sending it to a trained model.

Follow these steps:

1. Be sure you have downloaded this GitHub repository as specified in **Preliminaries** before you start.  Next, in your notebook instance, click the **New** button on the right and select **Folder**.  

2. Click the checkbox next to your new folder, click the **Rename** button above in the menu bar, and give the folder a name such as 'cifar-10'.

3. Click the folder to enter it.

4. To upload the notebook, click the **Upload** button on the right. Then in the file selection popup, select the file 'tf-distributed-training.ipynb' from the notebooks subdirectory in the folder on your computer where you downloaded this GitHub repository. Click the blue **Upload** button that appears to the right of the notebook's file name.

5. You are now ready to begin the notebook:  click the notebook's file name to open it, then follow the directions in the notebook.


<p><strong>NOTE:  some of the steps for this example typically take up to 10 minutes. Please wait for each notebook cell to complete before proceeding to run others.</strong></p>
