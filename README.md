# Amazon SageMaker Workshops

Amazon SageMaker is a fully managed service that enables developers and data scientists to quickly and easily build, train, and deploy machine learning models at any scale. This repository contains a collection of 2-hour workshops covering many features of Amazon SageMaker.  They are suitable for self-service or live, guided events.  

![Overview](./images/overview.png)

**BEFORE ATTEMPTING ANY WORKSHOP:  please review the Prerequisites below and complete any actions that are required, especially those in the Permissions section.**


# Workshops

- [**Introduction to Amazon SageMaker**](Introduction) - This 100-200 level workshop demonstrates some of the key features of Amazon SageMaker.  It does so via a set of straightforward examples for common use cases including: working with structured (tabular) data, natural language processing (sentiment analysis), and computer vision (image classification).  Content includes how to (1) do exploratory data analysis in Amazon SageMaker notebook environments such as SageMaker Studio or SageMaker Notebook Instances; (2) run Amazon SageMaker training jobs with your own custom models or built-in algorithms; and (3) get predictions using hosted model endpoints and batch transform jobs.

- [**TensorFlow in Amazon SageMaker**](TensorFlow) - In this 400 level workshop for experienced TensorFlow users, various aspects of TensorFlow usage in Amazon SageMaker will be demonstrated.  In particular, TensorFlow will be applied to a natural language processing use case, a structured data use case, and a computer vision use case.  Relevant SageMaker features that will be demonstrated include:  prototyping training and inference code with SageMaker Local Mode; SageMaker Pipelines for workflow orchestration; hosted training jobs for full-scale training; distributed training on a single multi-GPU instance or multiple instances; Automatic Model Tuning; batch and real time inference options.

- [**Simplify Workflows with Scripts, the CLI and Console**](Simplify-Workflows) - (**NOTE**:  for CI/CD in Amazon SageMaker and workflow orchestration, first consider [Amazon SageMaker Pipelines](https://aws.amazon.com/sagemaker/pipelines); an example is the Structured Data module of [**TensorFlow in Amazon SageMaker**](TensorFlow)). The focus of this 200+ level workshop is on simplifying Amazon SageMaker workflows, or doing ad hoc jobs, with a roll-your-own solution using scripts, the AWS CLI, and the Amazon SageMaker console.  All of these are alternatives to using Jupyter notebooks as an interface to Amazon SageMaker. You'll apply Amazon SageMaker built-in algorithms to a structured data example and a distributed training example showing different ways to set up nodes in a training cluster.


# Prerequisites

## AWS Account

**Permissions**: In order to complete this workshop you'll need an AWS Account, and an AWS IAM user in that account with at least full permissions to the following AWS services: 

- AWS IAM
- Amazon S3
- Amazon SageMaker
- AWS Step Functions
- AWS CloudShell or AWS Cloud9
- Amazon EC2:  including P3, C5, and M5 instance types; to check your limits, see [Viewing Your Current Limits](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-resource-limits.html).  If you do not have at least the default limits specified in [the Amazon SageMaker Limits table](https://docs.aws.amazon.com/general/latest/gr/sagemaker.html), please file a limit increase request via the AWS console.

**Use Your Own Account**: The code and instructions in this workshop assume only one student is using a given AWS account at a time. If you try sharing an account with another student, you'll run into naming conflicts for certain resources. You can work around these by appending a unique suffix to the resources that fail to create due to conflicts, but the instructions do not provide details on the changes required to make this work. Use a personal account or create a new AWS account for this workshop rather than using an organization’s account to ensure you have full access to the necessary services and to ensure you do not leave behind any resources from the workshop.

**Costs**: Some, but NOT all, of the resources you will launch as part of this workshop are eligible for the AWS free tier if your account is less than 12 months old. See the [AWS Free Tier page](https://aws.amazon.com/free/) for more details. An example of a resource that is **not** covered by the free tier is the Amazon SageMaker notebook instance type used in some workshops. To avoid charges for endpoints and other resources you might not need after you've finished a workshop, please refer to the [**Cleanup Guide**](./CleanupGuide). 


## AWS Region

Amazon SageMaker is not available in all AWS Regions at this time.  Accordingly, we recommend running this workshop in one of the following supported AWS Regions:  N. Virginia, Oregon, Ohio, Ireland or Sydney.

Once you've chosen a region, you should create all of the resources for this workshop there, including a new Amazon S3 bucket and a new SageMaker notebook instance. Make sure you select your region from the dropdown in the upper right corner of the AWS Console before getting started.

![Region selection screenshot](./images/region-selection.png)


## Browser

We recommend you use the latest version of Chrome or Firefox to complete this workshop.


## AWS Command Line Interface

To complete certain workshop modules, you'll need the AWS Command Line Interface (CLI) and a Bash environment. You'll use the AWS CLI to interface with Amazon SageMaker and other AWS services. Do NOT attempt to use a locally installed AWS CLI during a live workshop because there is insufficient time during a live workshop to resolve related issues with your laptop etc.

To avoid problems that can arise configuring the CLI on your machine during a live workshop, either [**AWS CloudShell**](https://aws.amazon.com/cloudshell/) or [**AWS Cloud9**](https://aws.amazon.com/cloud9/) can be used. AWS CloudShell is a browser-based shell that makes it easy to securely manage, explore, and interact with your AWS resources. To run Bash scripts for workshops using CloudShell, simply create raw text script files on your local computer, and then follow the instruction steps for [uploading and running script files](https://docs.aws.amazon.com/cloudshell/latest/userguide/getting-started.html).  

AWS Cloud9 is a cloud-based integrated development environment (IDE) that lets you write, run, and debug your code with just a browser. It has the AWS CLI pre-installed so you don’t need to install files or configure your laptop to use the AWS CLI. For Cloud9 setup directions, see [**Cloud9 Setup**](Cloud9). 


## Text Editor

For any workshop module that requires use of the AWS Command Line Interface (see above), you also will need a **plain text** editor for writing Bash scripts. Any editor that inserts Windows or other special characters potentially will cause scripts to fail. AWS Cloud9 includes a text editor, while for AWS CloudShell you'll need to use your own separate text editor of your choice to create script files (or enter commands one at a time). 


# License & Contributing

The contents of this workshop are licensed under the [Apache 2.0 License](./LICENSE). 
If you are interested in contributing to this project, please see the [Contributing Guidelines](./contributing/CONTRIBUTING.md).  In connection with contributing, also review the [Code of Conduct](./contributing/CODE_OF_CONDUCT.md).


