# 01. Ingest Data

Architecture 

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

Create connection for destination, Azure Blob 

### 2.2. Create Datasets

Click on '+ [add new factory resource]' button and click 'dataset'
Search 'HTTP' and click. And click 'Finish' to configure a source dataset.
Type name 'customer_churn_github' for the source dataset
Configure the connection for source dataset
Congifure Linked service and Request method
Congigure file format setting
* Check on 'Column names in the first row' check box

Configure the connection for destination dataset
Congifure Linked service and Request method
Congigure file format setting
* Check on 'Column names in the first row' check box

### 2.3. Create Pipeline

Create a new pipeline
Drag and drop 'Copy Data' from 'Move & Transform activity section
Click on the activity 'Copy Data' and select 'Source' tab in the bottom of the screen
Select customer_chrun_github' for 'Source Dataset'

## 3. Run the job

## 4. Monitor the job




---
[Next > 02. Data Wrangling](https://github.com/xlegend1024/az-cloudscale-adv-analytics/blob/master/02DataWrangling.md)

---
[Main](https://github.com/xlegend1024/az-cloudscale-adv-analytics/blob/master/README.md)
