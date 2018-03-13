# Built-in Algorithms Workshop

## Modules

This workshop is divided into multiple modules. After completing **Preliminaries**, complete the module **Creating a Notebook Instance** next.  You can complete the remaining module(s) in any order.  

- Preliminaries

- [**Creating a Notebook Instance**](../NotebookCreation) (Follow the link, then return here.)

- Parallelized Data Distribution 

## Preliminaries

- Be sure you have completed all of the Prerequisites listed in the [**main README**](../README.md).


- Download this repository to your computer by clicking the green **Clone or download** button from the upper right of the main page of the repository, then **Download ZIP**.

If you are new to using Jupyter notebooks, read the next section, otherwise you may now skip ahead to the next module.

### Jupyter Notebooks:  A Brief Overview

Jupyter notebooks tell a story by combining explanatory text and code. There are two types of "cells" in a notebook:  code cells, and "markdown" cells with explanatory text.  

You will be running the code cells.  These are distinguished by having "In" next to them in the left margin next to the cell, and a greyish background.  Markdown cells lack "In" and have a white background. To run a code cell, simply click in it, then either click the **Run Cell** button in the notebook's toolbar, or use Control+Enter from your computer's keyboard.  

It may take a few seconds to a few minutes for a code cell to run.  Please run each code cell in order, and **only once**, to avoid repeated operations.  For example, running the same training job cell twice might create two training jobs, possibly exceeding your service limits.

## Parallelized Data Distribution

1. **Exploratory Data Analysis**:  For this part of the module, we'll be using a SageMaker notebook instance to explore and visualize a data set.  To begin, in your notebook instance, click the **New** button on the right and select **Folder**.  

2. Click the checkbox next to your new folder, click the **Rename** button above in the menu bar, and give the folder a name such as 'distributed-data'.

3. Click the folder to enter it.

4. To upload the notebook for this module, click the **Upload** button on the right. Then in the file selection popup, select the file 'data_distribution_types.ipynb' from the notebooks subdirectory in the folder on your computer where you downloaded this GitHub repository. Click the blue **Upload** button that appears to the right of the notebook's file name.

5. You are now ready to begin the notebook:  click the notebook's file name to open it.

6. In the ```bucket = '<your_s3_bucket_name_here>'``` code line, paste the name of the S3 bucket you created in **Creating a Notebook Instance** to replace ```<your_s3_bucket_name_here>```.  The code line should now read similar to ```bucket = 'smworkshop-john-smith'```.  Do NOT paste the entire path (s3://.......), just the bucket name.  

7. Follow the directions in the notebook.  When it is time to set up a training job, return from the notebook to these instructions.  

8. **First Training Job**:  Now that we have our data in S3, we can begin training. We'll use SageMaker's Linear Learner algorithm. Since the focus of this module is data distribution to a training cluster and efficient loading of data, we'll fit two models in order to compare data distribution types: 

- In the first job, we'll use `FullyReplicated` for our `train` channel. This will pass every file in our input S3 location to every machine (in this case we're using 5 machines). 

- In the second job, we'll use `ShardedByS3Key` for the `train` channel (note that we'll keep `FullyReplicated` for the validation channel. So, for the training data, we'll pass each S3 object to a separate machine. Since we have 5 files (one for each year), we'll train on 5 machines, meaning each machine will get a year's worth of records.

Open a terminal window to enter commands.  [Windows users:  use PuTTY to connect to your Amazon Linux EC2 instance.]

9. Create a text file named `sm-cli.sh`. In the terminal window, change to the directory in which you created the file (if you're not already there), then run the following command :

```
chmod +x sm-cli.sh
```

10.  Paste the code snippet below into a text editor, and then change the text in the angle brackets (< >) as follows.  Do NOT put quotes around the values you insert.  
- arn_role:  (get from notebook instance in console).  It should look like the following:  `arn:aws:iam::1234567890:role/service-role/AmazonSageMaker-ExecutionRole-20171211T211964`.
- bucket:  the name of the S3 bucket you used in your notebook.  It should look like:  `s3://my-amazing-bucket`.

```
arn_role=<arn-of-your-notebook-role>
bucket=<name-of-your-s3-bucket>
prefix=/sagemaker/data_distribution_types
```

11.  Next, you'll specify the training code image and job name. Paste the following code into your text file just below the previous lines, replacing the training image with one specified below depending on the region in which you are running this lab:  
- N. Virginia:  382416733822.dkr.ecr.us-east-1.amazonaws.com/linear-learner:latest
- Oregon:  174872318107.dkr.ecr.us-west-2.amazonaws.com/linear-learner:latest
- Ohio:  404615174143.dkr.ecr.us-east-2.amazonaws.com/linear-learner:latest
- Ireland:  438346466558.dkr.ecr.eu-west-1.amazonaws.com/linear-learner:latest

```
training_image=<training-image-for-region>
training_job_name=linear-replicated-`date '+%Y-%m-%d-%H-%M-%S'`
```

12.  Paste the following code into your text file after the other lines:

```
training_data=$bucket$prefix/train
eval_data=$bucket$prefix/validation
train_source={S3DataSource={S3DataType=S3Prefix,S3DataDistributionType=FullyReplicated,S3Uri=$training_data}}
eval_source={S3DataSource={S3DataType=S3Prefix,S3DataDistributionType=FullyReplicated,S3Uri=$eval_data}}

aws sagemaker create-training-job \
--role-arn $arn_role \
--training-job-name $training_job_name \
--algorithm-specification TrainingImage=$training_image,TrainingInputMode=File \
--resource-config InstanceCount=5,InstanceType=ml.c4.2xlarge,VolumeSizeInGB=10 \
--input-data-config ChannelName=train,DataSource=$train_source,CompressionType=None,RecordWrapperType=None ChannelName=validation,DataSource=$eval_source,CompressionType=None,RecordWrapperType=None \
--output-data-config S3OutputPath=$bucket$prefix \
--hyper-parameters feature_dim=25,mini_batch_size=500,predictor_type=regressor,epochs=2,num_models=32,loss=absolute_loss \
--stopping-condition MaxRuntimeInSeconds=3600
    
```

13.  In your terminal window, run the following command, and then move onto the next step.

```
./sm-cli.sh.  
```

14. **Second Training Job**:  For our next training job with the `FullyReplicated` distribution type, please find and replace the following variables in the `sm-cli.sh` script with the code listed below:

```
training_job_name=linear-sharded-`date '+%Y-%m-%d-%H-%M-%S'`
train_source={S3DataSource={S3DataType=S3Prefix,S3DataDistributionType=ShardedByS3Key,S3Uri=$training_data}}
```

15.  In your terminal window, run the following command:

```
./sm-cli.sh.  
```

16.  In the SageMaker console, click **Jobs** in the left panel to check the status of the training jobs, which run concurrently.  When they are complete, their **Status** column will change from InProgress to Complete.  Duration of these jobs can last up to 8 or 9 minutes, including time for setting up the training cluster.

To check the actual training time for each job when both are complete, click the training job name in the jobs table, then examine the **Training time** listed at the top right under **Job Settings**.  As we can see, and might expect, the sharded distribution type trained substantially faster than the fully replicated type. This is a key differentiator to consider when preparing data and picking the distribution type.

17.  **SageMaker Model Creation**:  Now that we've trained our machine learning models, we'll want to make predictions by setting up a hosted endpoint for them. The first step in doing that is to point our hosting service to the model. We will point to the model.tar.gz that came from training, then create the hosting model.  We'll do this twice, once for each model we trained earlier. Here are the steps to do this via the SageMaker console:

[TBD]

17.  **Endpoint Configuration**:  Once we've setup our models, we can configure what our hosting endpoints should be. Here we specify the EC2 instance type to use for hosting, the initial number of instances, and our hosting model name.  Again, we'll do this twice, once for each model we trained earlier. Here are the steps to do this via the SageMaker console:

[TBD]

18.  **Endpoint Creation**:  Now that we've specified how our endpoints should be configured, we can create them.

19.  **Evaluation**:  To compare predictions from our two models, let's return to the notebook we used earlier.  When you are finished, return here and proceed to the Cleanup section.  


## Cleanup

To avoid charges for endpoints and other resources you might not need after the workshop, please refer to the [**Cleanup Guide**](../CleanupGuide).






