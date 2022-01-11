---
description: Description of Custom AWS Cloudformation Templates
---

# ☁ AWS CloudFormation Templates

Add Custom CFN templates here if you made any. Please explain briefly what they do.

This template creates SSM Parameters to pass the names of the DynamoDB tables to the Backend ETL.

```json
{
  "AWSTemplateFormatVersion": "2010-09-09",
  "Description": "An auto-generated nested stack.",
  "Metadata": {},
  "Parameters": {
    "AppSyncApiId": {
      "Type": "String",
      "Description": "The id of the AppSync API associated with this project."
    },
    "AppSyncApiName": {
      "Type": "String",
      "Description": "The name of the AppSync API",
      "Default": "AppSyncSimpleTransform"
    },
    "env": {
      "Type": "String",
      "Description": "The environment name. e.g. Dev, Test, or Production",
      "Default": "NONE"
    },
    "S3DeploymentBucket": {
      "Type": "String",
      "Description": "The S3 bucket containing all deployment assets for the project."
    },
    "S3DeploymentRootKey": {
      "Type": "String",
      "Description": "An S3 key relative to the S3DeploymentBucket that points to the root\nof the deployment directory."
    },
    "ProjectName": {
      "Type": "String",
      "Description": "Name of this Amplify Project"
    }
  },
  "Resources": {
    "EmptyResource": {
      "Type": "Custom::EmptyResource",
      "Condition": "AlwaysFalse"
    },
    "CensusTableNameParameter": {
      "Type": "AWS::SSM::Parameter",
      "Properties": {
        "Name": {
          "Fn::Sub": "/amplify/${ProjectName}/${env}/censusDB"
        },
        "Type": "String",
        "Value": {
          "Fn::ImportValue": {
            "Fn::Sub": "${AppSyncApiId}:GetAtt:CensusDataEntryTable:Name"
          }
        },
        "Description": "Census Data DynamoDB Table Name"
      }
    },
    "DonationDataEntryTableParameter": {
      "Type": "AWS::SSM::Parameter",
      "Properties": {
        "Name": {
          "Fn::Sub": "/amplify/${ProjectName}/${env}/donationDB"
        },
        "Type": "String",
        "Value": {
          "Fn::ImportValue": {
            "Fn::Sub": "${AppSyncApiId}:GetAtt:DonationDataEntryTable:Name"
          }
        },
        "Description": "Donation Data DynamoDB Table Name"
      }
    }
  },
  "Conditions": {
    "HasEnvironmentParameter": {
      "Fn::Not": [
        {
          "Fn::Equals": [
            {
              "Ref": "env"
            },
            "NONE"
          ]
        }
      ]
    },
    "AlwaysFalse": {
      "Fn::Equals": ["true", "false"]
    }
  },
  "Outputs": {
    "EmptyOutput": {
      "Description": "An empty output. You may delete this if you have at least one resource above.",
      "Value": ""
    }
  }
}
```
