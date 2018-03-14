# Amazon SageMaker Workshops

Amazon SageMaker is a fully managed service that enables developers and data scientists to quickly and easily build, train, and deploy machine learning models at any scale. This repository contains a collection of workshops and other hands on content that will guide you through using the many features of SageMaker.  

![Overview](./images/overview.png)

You'll start by creating a SageMaker notebook instance with the requisite permissions. Depending on the workshop, you will then interact with SageMaker via sample Jupyter notebooks, the AWS CLI, the SageMaker console, or all three. During a workshop, you'll explore various data sets, create model training jobs using SageMaker's hosted training feature, and create endpoints to serve predictions from your models using SageMaker's hosted endpoint feature.  

**BEFORE attempting any of the workshops, please review the Prequisites below and complete any action that are required.**

# Workshops

- [**Introduction to SageMaker**](Introduction) - This workshop demonstrates the main features of SageMaker via a set of straightforward examples for common use cases.


- [**Introduction to SageMaker (Advanced)**](Introduction-Advanced) - [COMING SOON] This workshop is targeted to experienced data scientists. It demonstrates the main features of SageMaker via a set of advanced examples for more complex use cases.


- [**SageMaker Built-in Algorithms**](Built-in-Algorithms) - This workshop shows you how to use some of SageMaker's built-in algorithms. These algorithms are ready-to-use, scalable, and provide many other conveniences. 

# Prerequisites

BEFORE beginning any of the workshops, please review the following and complete any actions that are required.

## AWS Account

In order to complete this workshop you'll need an AWS Account with access to create AWS IAM, S3 and SageMaker resources. The code and instructions in this workshop assume only one student is using a given AWS account at a time. If you try sharing an account with another student, you'll run into naming conflicts for certain resources. You can work around these by appending a unique suffix to the resources that fail to create due to conflicts, but the instructions do not provide details on the changes required to make this work.

Some of the resources you will launch as part of this workshop are eligible for the AWS free tier if your account is less than 12 months old. See the [AWS Free Tier page](https://aws.amazon.com/free/) for more details.

## AWS Region

SageMaker is not available in all AWS Regions at this time.  Accordingly, we recommend running this workshop in one of the following supported AWS Regions:  N. Virginia, Oregon, Ohio, or Ireland.

Once you've chosen a region, you should create all of the resources for this workshop there, including a new Amazon S3 bucket and a new SageMaker notebook instance. Make sure you select your region from the dropdown in the upper right corner of the AWS Console before getting started.

![Region selection screenshot](./images/region-selection.png)

## Browser

We recommend you use the latest version of Chrome or Firefox to complete this workshop.

## AWS Command Line Interface

To complete certain workshops, you'll need the AWS Command Line Interface (CLI) installed on your local machine. You'll use the CLI to interface with SageMaker and other AWS services. At this time, only the following workshops require use of the CLI:  **SageMaker Built-in Algorithms** workshop.

Follow the [AWS CLI Getting Started](http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-set-up.html) guide to install and configure the CLI on your machine.

WINDOWS USERS NOTE:  For workshops that use the AWS CLI, Bash scripts are utilized. You can either setup your local Windows computer with Bash, OR for the CLI-based portions of the workshop use a cloud-based EC2 instance with the Amazon Linux AMI, which comes with the AWS CLI pre-installed. Connect to your EC2 instance with PuTTY or a similar tool, and then upgrade the AWS CLI with the command `sudo pip install --upgrade awscli`, and configure it per the above instructions.  

## Text Editor

For any workshop that requires use of the AWS Command Line Interface (see above), you also will need a **plain text** editor for writing Bash scripts. Make sure the text editor supports plain text because any editor that inserts Windows or other special characters potentially will cause scripts to fail.


# License & Contributing

The contents of this workshop are licensed under the [Apache 2.0 License](./LICENSE). 
If you are interested in contributing to this project, please see the [Contributing Guidelines](./contributing/CONTRIBUTING.md).  In connection with contributing, also review the [Code of Conduct](./contributing/CODE_OF_CONDUCT.md).


