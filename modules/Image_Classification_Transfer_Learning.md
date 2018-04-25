## Image Classification 


For this module, we'll work with an image classification example notebook. In particular, we'll use Amazon SageMaker's built-in image classification algorithm, which is a supervised learning algorithm that takes an image as input and classifies it into one of multiple output categories. 

It uses a convolutional neural network (ResNet) that can be trained from scratch, or trained using transfer learning.  The technique of transfer learning is useful when a large number of training images are not available. Even if you don't have experience with neural networks or image classification, SageMaker's image classification algorithm makes the technology easy to use, with no need to design and set up your own neural network.  

Follow these steps:

1. Be sure you have downloaded this GitHub repository as specified in **Preliminaries** before you start.  Next, in your notebook instance, click the **New** button on the right and select **Folder**.  

2. Click the checkbox next to your new folder, click the **Rename** button above in the menu bar, and give the folder a name such as 'image-classification'.

3. Click the folder to enter it.

4. To upload the notebook, click the **Upload** button on the right. Then in the file selection popup, select the file 'Image-classification-transfer-learning.ipynb' from the notebooks subdirectory in the folder on your computer where you downloaded this GitHub repository. Click the blue **Upload** button that appears to the right of the notebook's file name.

5. You are now ready to begin the notebook:  click the notebook's file name to open it, then follow the directions in the notebook.


<p><strong>NOTE:  training the model for this example typically takes about 10 minutes.</strong> However, keep in mind that this is relatively short because transfer learning is used rather than training from scratch, which could take many hours.</p>

