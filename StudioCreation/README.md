# Creating an Amazon SageMaker Studio domain

SageMaker Studio is an IDE for machine learning. To create a SageMaker Studio domain for this workshop, follow these steps:

- Go to https://docs.aws.amazon.com/sagemaker/latest/dg/onboard-quick-start.html
- Follow the directions for the first several steps, when you reach reach the "For **Execution role**" step, be sure to carefully read the bullet point below first.
- For **Execution role**, choose **Create a new role**, leave the defaults on the pop up, and click **Create role**.
- When creation is complete (this may take about five minutes), click **Open Studio** in the line for your default user.
- Open a terminal within Studio (File menu -> New -> Terminal).
- Clone the official samples repository with this command:

```
git clone https://github.com/awslabs/amazon-sagemaker-workshop.git
```

- Return to the main workshop instructions page and continue with the rest of the workshop.
