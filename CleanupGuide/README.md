
# Cleanup Guide

To avoid charges for resources you no longer need when you're done with this workshop, you can delete them or, in the case of your notebook instance, stop them.  Below is a list of the resources you should check.  Please go through them in order to make sure you do not incur charges unnecessarily:


- **Endpoints**:  These are the clusters of one or more instances serving inferences from your models. If you did not delete them from within a notebook, you can delete them via the SageMaker console.  To do so:

  - Click the **Endpoints** link in the left panel.  
  
  - Then, for each endpoint, click the radio button next to it, then select **Delete** from the **Actions** drop down menu. 
  
  - You can follow a similar procedure to delete the related Models and Endpoint configurations.


- **SageMaker Studio**:  Follow these instructions if you created a SageMaker Studio domain, rather than a SageMaker Notebook Instance.  SageMaker Studio charges mainly accrue for resources that are running in the SageMaker Studio domain.  Accordingly, you have two options:

  - To **shut down** resources in the domain:  Follow the instructions for **Shut Down Resources** at https://docs.aws.amazon.com/sagemaker/latest/dg/notebooks-run-and-manage-shut-down.html.  

  - To **delete** the SageMaker Studio domain:  If you do not expect to use the domain, you may completely delete it.  Follow the instructions at https://docs.aws.amazon.com/sagemaker/latest/dg/gs-studio-delete-domain.html.   
  

- **Notebook instance**:  Follow these instructions if you created a SageMaker notebook instance, rather than a SageMaker Studio domain.  You have two options if you do not want to keep the notebook instance running. If you would like to save it for later, you can stop rather than deleting it. 

  - To **stop** a notebook instance:  Click the **Notebook instances** link in the left pane of the SageMaker console home page. Next, click the **Stop** link under the 'Actions' column to the left of your notebook instance's name.  After the notebook instance is stopped, you can start it again by clicking the **Start** link.  Keep in mind that if you stop rather than delete it, you will be charged for the storage associated with it.  

  - To **delete** a notebook instance:  First stop it per the instruction above. Next, click the radio button next to your notebook instance, then select **Delete** from the **Actions** drop down menu. 
  
  
- **S3 Bucket**:  If you retain the S3 bucket created for this workshop, you will be charged for storage.  To avoid these charges if you no longer wish to use the bucket, you may delete it. To delete the bucket, go to the S3 service console, and locate your bucket's name in the bucket table. Next, click in the bucket table row for your bucket to highlight the table row. At the top of the table, the **Delete Bucket** button should now be enabled, so click it and then click the **Confirm** button in the resulting pop-up to complete the deletion.  
  
  
  
