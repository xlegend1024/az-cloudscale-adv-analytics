# 01. Ingest Data

## Architecture 

## 0. Access to Azure Portal

Go to [Azure Portal](https://azure.portal.com) for lab.

## 1. Create Azure Data Factory

## 2. Create Data Pipeline

Create connections, datasets for source and destination. And then create pipeline that copies source data to destination.

### 2.1. Create Connections

__Click__ 'Connections' icon bottom of lift coner.
__Search__ 'HTTP' and click. And click 'Continue' to configure a source dataset.
__Create__ connection for source, web service
    Use following link for 'Base URL'

```
https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-2017 
```

__Select__ 'Anonymous' for 'Authentication type'
__Click__ 'Finish'
__Create__ connection for destination, Azure Blob 

### 2.2. Create Datasets

__Click__ on '+ [add new factory resource]' button and click 'dataset'
__Search__ 'HTTP' and click. And click 'Finish' to configure a source dataset.
__Type__ name 'customer_churn_github' for the source dataset
Configure the connection for source dataset
Congifure Linked service and Request method
Congigure file format setting
* __Check__ on 'Column names in the first row' check box

Configure the connection for destination dataset
Congifure Linked service and Request method
Congigure file format setting
* __Check__ on 'Column names in the first row' check box

### 2.3. Create Pipeline

__Create__ a new pipeline
__Drag and drop__ 'Copy Data' module from 'Move & Transform activity section to canvas
__Click__ on the activity 'Copy Data' and select 'Source' tab in the bottom of the screen
__Select__ customer_chrun_github' for 'Source Dataset'

## 3. Run the job

To manualy start the data pipeline, __Click__ on _'Trigger Now'_ of _'Trigger'_ and then click _'Finish'_ to run the pipeline.

## 4. Monitor the job

From the lift panel, __click__ monitor icon to see pipeline run status and history of jobs
To see detail logs of activies in pipeline, __click__ on pipeline icon
__Click__ on _input_, _output_ and _detail_ to see raw log of the activities 

---
[Next > 02. Data Wrangling](https://github.com/xlegend1024/az-cloudscale-adv-analytics/blob/master/02DataWrangling.md)

---
[Main](https://github.com/xlegend1024/az-cloudscale-adv-analytics/blob/master/README.md)
