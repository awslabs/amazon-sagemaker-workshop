# Built-in Algorithms Workshop

## Modules

This workshop is divided into multiple modules. **Creating a Notebook Instance** must be completed first, followed by **Video Game Sales**.  You can complete the other modules in any order.  

- [**Creating a Notebook Instance**](../NotebookCreation) (Follow the link, then return here.)

- Parallelized Data Distribution 

- ( TBD ) 

Be patient as you work your way through the notebook-based modules. After you run a cell in a notebook, it may take several seconds for the code to show results. For the cells that start training jobs, it may take several minutes. In particular, the last two modules have training jobs that may last up to 10 minutes.  

After you have completed the workshop, you can delete all of the resources that were created by following the Cleanup Guide provided with this lab guide. 

## Parallelized Data Distribution

Paste the code snippet below into a text editor, and then change the text in the angle brackets (< >) as follows.  Do NOT put quotes around the values you insert.  
- arn_role:  (get from notebook instance in console).  It should look like the following:  `arn:aws:iam::1234567890:role/service-role/AmazonSageMaker-ExecutionRole-20171211T211964`.
- bucket:  the name of the S3 bucket you used in your notebook.  It should look like:  `s3://my-amazing-bucket`.

```
arn_role=<arn-of-your-notebook-role>
bucket=<name-of-your-s3-bucket>
prefix=/sagemaker/data_distribution_types
```

Next, you'll specify the training code image and job name. Paste the following code into your text file just below the previous lines, replacing the training image with one specified below depending on the region in which you are running this lab:  
- N. Virginia:  382416733822.dkr.ecr.us-east-1.amazonaws.com/linear-learner:latest
- Oregon:  174872318107.dkr.ecr.us-west-2.amazonaws.com/linear-learner:latest
- Ohio:  404615174143.dkr.ecr.us-east-2.amazonaws.com/linear-learner:latest
- Ireland:  438346466558.dkr.ecr.eu-west-1.amazonaws.com/linear-learner:latest

```
training_image=<training-image-for-region>
training_job_name=linear-sharded-`date '+%Y-%m-%d-%H-%M-%S'`
```

Finally, paste the following code into your text file after the other lines:

```
training_data=$bucket$prefix/train
eval_data=$bucket$prefix/validation
train_source={S3DataSource={S3DataType=S3Prefix,S3DataDistributionType=ShardedByS3Key,S3Uri=$training_data}}
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

Run the command chmod +x, then ./sm-cli.sh.  


## Cleanup

To avoid charges for endpoints and other resources you might not need after the workshop, please refer to the [**Cleanup Guide**](../CleanupGuide).






