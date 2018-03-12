# Amazon SageMaker Workshops

Amazon SageMaker is a fully managed service that enables developers and data scientists to quickly and easily build, train, and deploy machine learning models at any scale. This repository contains a collection of workshops and other hands on content that will guide you through using the many features of SageMaker.  

![Overview](./images/overview.png)

You'll start by creating a SageMaker notebook instance with the requisite permissions. You will then interact with SageMaker via sample Jupyter notebooks, the AWS CLI, and the SageMaker console. For example, you'll create model training jobs using SageMaker's hosted training feature, and create endpoints to serve predictions from your models using SageMaker's hosted endpoint feature.  

# Workshops

- [**Introduction to SageMaker**](Introduction) - This workshop demonstrates the main features of SageMaker via a set of straightforward examples for common use cases.


- [**Introduction to SageMaker (Advanced)**](Introduction-Advanced) - [COMING SOON] This workshop is targeted to experienced data scientists. It demonstrates the main features of SageMaker via a set of advanced examples for more complex use cases.


- [**SageMaker Built-in Algorithms**](Built-in-Algorithms) - This workshop shows you how to use some of SageMaker's built-in algorithms.  

## Prerequisites

### AWS Account

In order to complete this workshop you'll need an AWS Account with access to create AWS IAM, S3 and SageMaker resources. The code and instructions in this workshop assume only one student is using a given AWS account at a time. If you try sharing an account with another student, you'll run into naming conflicts for certain resources. You can work around these by appending a unique suffix to the resources that fail to create due to conflicts, but the instructions do not provide details on the changes required to make this work.

Some of the resources you will launch as part of this workshop are eligible for the AWS free tier if your account is less than 12 months old. See the [AWS Free Tier page](https://aws.amazon.com/free/) for more details.

### AWS Region

SageMaker is not available in all AWS Regions at this time.  Accordingly, we recommend running this workshop in one of the following supported AWS Regions:  N. Virginia, Oregon, Ohio, or Ireland.

Once you've chosen a region, you should create all of the resources for this workshop there, including a new Amazon S3 bucket and a new SageMaker notebook instance. Make sure you select your region from the dropdown in the upper right corner of the AWS Console before getting started.

![Region selection screenshot](./images/region-selection.png)

### Browser

We recommend you use the latest version of Chrome or Firefox to complete this workshop.

## License & Contributing

The contents of this workshop are licensed under the [Apache 2.0 License](./LICENSE). 
If you are interested in contributing to this project, please see the [Contributing Guidelines](./contributing/CONTRIBUTING.md).  In connection with contributing, also review the [Code of Conduct](./contributing/CODE_OF_CONDUCT.md).


