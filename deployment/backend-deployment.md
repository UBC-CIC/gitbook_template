# Backend Deployment

## Backend/Data Preparation Deployment

### Step 1: Clone this repository

### Step 2: Deploy CloudFormation template

1.  In a terminal in the project root directory, enter the following command. This will guide you through the deployment process. The CloudFormation template will create a Step Function and the Lambda functions it triggers to fetch and prepare the census and T1 data.

    Parameter details:

    - _Stack Name_: An identifier for your stack.
    - _AWS Region_: The region where the solution will be deployed.
    - _AmplifyAppName_: The name of the Amplify app created previously.
    - _AmplifyBackendEnv_: The name of the Amplify backend environment of the app created previously.

    To find _AmplifyAppName_ and _AmplifyBackendEnv_, go to the Amplify console, and click on the app you created during frontend deployment. In the example provided below, the app is called "census-explorer", and the backend environment is called "devu"

![](<../assets/BE_deploy_1.png)

```
sam deploy --template step-fcn-template.yaml --guide
```

![](<../assets/BE_deploy_2.png)

**Note:** Make sure this step completes successfully before moving on to the next step.

1. When the deployment is complete, a parameter with the key _BucketName_ will be output. This is the bucket you will be uploading data to in the future, so remember the name

![](<../assets/BE_deploy_3.png)

### Step 3: Upload files for data preparation

1\. Log in to the S3 management console.

2\. \***\* Select the bucket created by the CloudFormation template in step 2.2. Click **Create folder**, and name it "unprocessed-data**".\*\*

![](<../assets/BE_deploy_4.png)

![](<../assets/BE_deploy_5.png)

3\. Select the new _unprocessed-data_ folder. Click **Upload**, and add the "headers.csv", "Donations by Family Type - 2006 to 2018 (FSAs).csv", and "Donations by Income Group - 2006 to 2018 (FSAs).csv" files from the data directory of this repository

![](<../assets/BE_deploy_6.png)

![](<../assets/BE_deploy_7.png)

![](<../assets/BE_deploy_8.png)

**Note:** Make sure the files finish uploading before moving on to the next step.

### Step 4: Trigger data preparation Step Function

1. Log in to the Lambda management console. Select **Step Functions state machines** from the menu on the left.
2. Select the state machine - the name should start with "DataProcessingStateMachine-".
3. Click **Execute**. Leave all settings at default.

Once the state machine finishes executing successfully, backend deployment and data preparation is complete!
