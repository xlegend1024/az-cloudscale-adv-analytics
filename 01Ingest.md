# 01. Ingest Data

## Architecture

    In this lab, we'll build data movement pipeline in *Azure Data Factory* to move data from a web service to Blob.

## 0. Access to Azure Portal

Go to [Azure Portal](https://azure.portal.com) for this lab.

## 1. Create Azure Data Factory

__Click__ on '+ Create a resource' icon on the left panel, and __search __ _Data Factory_ from the search bar

![00](./images/01.00.png)

__Select__ _Data Factory_ and __click__ _create_ button, then you'll see New data factory blades

Fill out the from and __click__ on _Create_

![01](./images/01.01.png)

When the Data Facotry is created, pin it to dashboard so you can access the service eay

![02](./images/01.02.png)

## 2. Create Data Pipeline

Create connections, datasets for source and destination. And then create pipeline that copies source data to destination.

__Open__ the Data Factory and __click__ on _Author&Monitor_ link form the blades

![03](./images/01.03.png)

### 2.1. Create Connections

__Click__ on _Author_  and then __click__ _Connections_ at the bottom of the screen

![04](./images/01.04.png)

To add new _Linked services_ (e.g. connection string), __click__ on _+ NEW_

An then __Search__ 'HTTP' from the search bar and select the _HTTP_ and then click 'Continue' to configure a source dataset.

![05](./images/01.05.png)

__Create__ connection for source, name it as 'src_web_churn_csv'

Use following link for 'Base URL'

```
https://raw.githubusercontent.com/Azure/MachineLearningSamples-ChurnPrediction/master/data/CATelcoCustomerChurnTrainingSample.csv
```

__Select__ 'Anonymous' for 'Authentication type'

__Click__ 'Finish'

![06](./images/01.06.png)

Add new _Linked services_ for Azure blob which will be used for store source data
__click__ on _+ NEW_ and search Blob

![06](./images/01.06.png)

__Create__ connection for destination, name it as 'dst_blob_datalake'

![08](./images/01.08.png)

### 2.2. Create Datasets

2.2.1. Create Source dataset 

__Click__ on '+ [add new factory resource]' button and click 'Dataset' to create source dataset

![09](./images/01.09.png)

__Search__ 'HTTP' and click. And click 'Finish' to configure a source dataset

__Type__ name 'web_churn_csv' for the source dataset

![10](./images/01.10.png)

Configure _Linked Service_ for the connection of this source dataset which is 'src_web_churn_csv'

![11](./images/01.11.png)

* __Check__ on 'Column names in the first row' check box

![12](./images/01.12.png)

2.2.2. Create Destination dataset

__Click__ on '+ [add new factory resource]' button and click 'Dataset' to create destination dataset

![13](./images/01.13.png)

__Search__ 'Blob' and click. And click 'Finish' to configure a destination dataset

__Type__ name 'blob_churn_csv' for the destination dataset

__Click__ on _Connection_ tab to configure _Linked Service_ for the connection of destination dataset which is 'dst_blob_datalake'

![14](./images/01.14.png)

__Type__ 'ingest' for folder and 'customerchurnsource.csv' for file name

![1401](./images/01.14.01.png)

__Check__ on 'Column names in the first row' check box

![15](./images/01.15.png)

### 2.3. Create Pipeline

To __Create__ a new pipeline, __click__ on '+ [add new factory resource]' and then __click__ 'Pipeline'

![16](./images/01.16.png)

Name the pipeline as 'copy_churn_web__blob'

![17](./images/01.17.png)

__Drag and drop__ 'Copy Data' module from 'Move & Transform activity section to canvas

![18](./images/01.18.png)

Name the activity as 'Copy Data Activity'

![19](./images/01.19.png)

__Click__ on the activity 'Copy Data Activity', __select__ 'Source' tab in the bottom of the screen and then __select__ 'web_churn_csv' for the 'Source Dataset'

![20](./images/01.20.png)

__Click__ 'Sink' tab and __select__ 'blob_churn_csv' for the 'Sink Dataset'

![21](./images/01.21.png)

__Click__ 'Publishing' button

![22](./images/01.22.png)

## 3. Run the job

To manualy start the data pipeline, __Click__ on _'Trigger Now'_ of _'Trigger'_ and then click _'Finish'_ to run the pipeline.

![23](./images/01.23.png)

## 4. Monitor the job

From the lift panel, __click__ monitor icon to see pipeline run status and history of jobs

![24](./images/01.24.png)

To see detail logs of activies in pipeline, __click__ on pipeline icon

![26](./images/01.26.png)

__Click__ on _input_, _output_ and _detail_ to see raw log of the activities 

![27](./images/01.27.png)

---
[Next > 02. Data Wrangling](https://github.com/xlegend1024/az-cloudscale-adv-analytics/blob/master/02DataWrangling.md)

---
[Main](https://github.com/xlegend1024/az-cloudscale-adv-analytics/blob/master/README.md)
