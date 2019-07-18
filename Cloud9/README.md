# AWS Cloud9 IDE

AWS Cloud9 is a cloud-based integrated development environment (IDE) that lets you write, run, and debug your code with just a browser. It includes a code editor, debugger, and terminal. Cloud9 comes prepackaged with essential tools for popular programming languages and the AWS Command Line Interface (CLI) pre-installed so you don’t need to install files or configure your laptop for this workshop. Your Cloud9 environment will have access to the same AWS resources as the user with which you logged into the AWS Management Console.

Take a moment now and setup your Cloud9 development environment.

## Step-by-step Instructions

- Go to the AWS Management Console, click **Services** then select **Cloud9** under Developer Tools.


- Click **Create environment**.


- Enter `Development` into **Name** and optionally provide a **Description**.


- Click **Next step**.


- You may leave **Environment settings** at their defaults of launching a new **t2.micro** EC2 instance which will be paused after **30 minutes** of inactivity.


- Click **Next step**.


- Review the environment settings and click **Create environment**. It will take several minutes for your environment to be provisioned and prepared.


- Once ready, your IDE will open to a welcome screen. The central panel of the IDE has two parts:  a text/code editor in the upper half, and a terminal window in the lower half. Below the welcome screen in the editor, you should see a terminal prompt similar to the following (you may need to scroll down below the welcome screen to see it):

![Terminal](./images/setup-cloud9-terminal.png)

- You can run AWS CLI commands in here just like you would on your local computer. Verify that your user is logged in by running `aws sts get-caller-identity` as follows at the terminal prompt:

```
aws sts get-caller-identity
```

- You’ll see output indicating your account and user information:

```
Admin:~/environment $ aws sts get-caller-identity

{
    "Account": "123456789012",
    "UserId": "AKIAI44QH8DHBEXAMPLE",
    "Arn": "arn:aws:iam::123456789012:user/Alice"
}
```


- To create a new text/code file, just click the **+** symbol in the tabs section of the editor part of the IDE. You can do that now, and close the wecome screen by clicking the **x** symbol in the welcome screen tab.


- Keep your AWS Cloud9 IDE opened in a browser tab throughout this workshop as we’ll use it for activities like using the AWS CLI and running Bash scripts.

## Tips

Keep an open scratch pad in Cloud9 or a text editor on your local computer for notes. When the step-by-step directions tell you to note something such as an ID or Amazon Resource Name (ARN), copy and paste that into the scratch pad.







