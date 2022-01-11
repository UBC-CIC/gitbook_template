---
description: High Level Solution Overview
---

# 🔬 Solution Overview

Put a high level overview of your solution here. It is nice to separate into logical blocks so a reader is not overwhelmed with info.

Example from Census Explorer:

### Stack Overview

**Frontend**: The ReactJS framework was used to develop the frontend of the application. AWS Amplify was used to interface with other Amazon Web Services such as Amazon S3, AWS Lambda and Amazon DynamoDB. The library used to display the map is react-leaflet / leaflet.js, which has a GeoJSON layer attached. All other components were developed in React from scratch. For more info on the frontend, see [Frontend Architecture](https://github.com/UBC-CIC/census-explorer/blob/master/docs/FrontendArchitecture.md).

**Data Preparation**: All data was initially processed using an AWS Step Function running a sequence of AWS Lambdas. For more information on the data preparation process, see [Backend ETL](https://github.com/UBC-CIC/census-explorer/blob/master/docs/BackendETL.md).

**Data Storage**: All data is saved in Amazon S3 and Amazon DynamoDB. Namely, GeoJSON files are stored in Amazon S3, and Census/T1 data is stored in Amazon DynamoDB.

**Data Processing**: The backend has AWS Lambda functions to process incoming data from Amazon DynamoDB, fetched through a GraphQL API.

### Architecture Diagram

Put an image of any (top level) architecture diagrams here:
![High Level Architecture](https://placekitten.com/500/500)
