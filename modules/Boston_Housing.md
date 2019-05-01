## Bosting Housing:  Predicting House Prices 

In this module, we'll train and test a regression model to predict house prices using Amazon SageMaker's prebuilt TensorFlow container. We'll use Script Mode, which allows you to simply bring your own Python training script similar to one you would use outside Amazon SageMaker.  In Script Mode, you can use the [SageMaker Python SDK](https://github.com/aws/sagemaker-python-sdk) to abstract away many of the low level details of setting up training jobs and endpoints.   

1. Be sure you have downloaded this GitHub repository as specified in **Preliminaries** before you start.  Next, in your notebook instance, click the **New** button on the right and select **Folder**.

2. Click the checkbox next to your new folder, click the **Rename** button above in the menu bar, and give the folder a name such as 'boston-housing'.

3. Click the folder to enter it.

4. To upload the notebook, click the **Upload** button on the right. Then in the file selection popup, select the file 'tf-boston-housing.ipynb' from the notebooks subdirectory in the folder on your computer where you downloaded this GitHub repository. Click the blue **Upload** button that appears to the right of the notebook's file name.

5. You are now ready to begin the notebook:  click the notebook's file name to open it, then follow the directions in the notebook.


<p><strong>NOTE:  initial hosted model training for this example typically takes about 5 minutes; the Automatic Model Tuning job can take up to 10 minutes.</strong></p>
