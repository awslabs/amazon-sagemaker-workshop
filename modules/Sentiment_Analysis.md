## Sentiment Analysis 

In this module, we'll train and test a Sentiment Analysis (Text Classification) model on SageMaker using SageMaker's prebuilt Deep Learning containers. These containers are available for TensorFlow, MXNet, PyTorch, and Chainer. 

With this approach, you simply bring your own Python training script, and SageMaker handles the rest.  All of this is simplied using the conveniences provided by the [SageMaker Python SDK](https://github.com/aws/sagemaker-python-sdk), which abstracts away many of the low level details of setting up training jobs and endpoints.   

1. Be sure you have downloaded this GitHub repository as specified in **Preliminaries** before you start.  Next, in your notebook instance, click the **New** button on the right and select **Folder**.

2. Click the checkbox next to your new folder, click the **Rename** button above in the menu bar, and give the folder a name such as 'sentiment-analysis'.

3. Click the folder to enter it.

4. To upload the notebook, click the **Upload** button on the right. Then in the file selection popup, select the file 'sentiment-analysis.ipynb' from the notebooks subdirectory in the folder on your computer where you downloaded this GitHub repository. Click the blue **Upload** button that appears to the right of the notebook's file name.

5. You are now ready to begin the notebook:  click the notebook's file name to open it, then follow the directions in the notebook.


<p><strong>NOTE:  training the model for this example typically takes about 5 minutes.</strong></p>
