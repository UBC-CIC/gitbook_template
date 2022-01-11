# Frontend Deployment

## Requirements

For deployment:

* [AWS Account](https://aws.amazon.com/account/)
* [GitHub Account](https://github.com)
* [SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html) (**Note:** _Step 3: Install Docker_ is not required)

For prototyping:

* [Python 3.7 or greater](https://realpython.com/installing-python/)

## Frontend Deployment

### Create a Service Role

Please create a new service role in your AWS Account.

1. Log into the AWS Console on your AWS Account with IAM Permissions.

![](<../.gitbook/assets/image (13).png>)



2\. Search for IAM and click on the first suggestion.&#x20;

![](<../.gitbook/assets/image (12).png>)

3\. Click on Roles in the left sidebar.

![](<../.gitbook/assets/image (17).png>)

4\. Click on Create Role

5\. Scroll down and click on Amplify

![](<../.gitbook/assets/image (20).png>)

6\. Click next until you get to the Review page. Name the role: This example uses 'censusexplorer-amplify-backend-role'

![](<../.gitbook/assets/image (1).png>)

7\. Click Create Role.

8\. Find your new role by searching for it in the roles search bar. Click on it.

![](<../.gitbook/assets/image (3).png>)

9\. Click on Add inline policy

10\. Click on the JSON tab, and replace the text box with the contents of [this file](https://github.com/UBC-CIC/census-explorer/blob/master/docs/servicePolicy.json).

11\. Click on Review Policy, and name it appropriately. Eg: 'census-explorer-backend-policy'

12\. Click on Create Policy. You should see something similar to this:

![](<../.gitbook/assets/image (14).png>)

### Deploy the Frontend

To deploy the frontend of this solution into your AWS Account, press the following button:

[![amplifybutton](https://camo.githubusercontent.com/2e4b3df55d355659b3d677e3abf7808b43b055d6131a01c8def0f1316d2da8f5/68747470733a2f2f6f6e65636c69636b2e616d706c6966796170702e636f6d2f627574746f6e2e737667)](https://console.aws.amazon.com/amplify/home#/deploy?repo=https://github.com/UBC-CIC/census-explorer)

This should take you to the following screen: Click on **Connect to Github** and log in to your Github Account.

![](../.gitbook/assets/image.png)

**From the dropdown, make sure to choose the role that you just made!**

![](<../.gitbook/assets/image (16).png>)

Click on save and deploy.
