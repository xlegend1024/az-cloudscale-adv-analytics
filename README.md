# Cloud Scale Advanced Analtyics

Experience end-to-end Advanced Analytics on cloud using Blob, ADF, Databricks, SQLDB/DW and Azure Machine Leaning Studio.

Thu out this hands on lab Understand how to apply followings for you work:

* Azure Data Factory
* Azure Databricks
* Azure SQL Database
* Azure ML Studio
* Azure Key Vault

After the workshop you will be able to:

1. Understand process and architecture for cloud scale andvanced analaytics project
1. Create appropreate Azure services for data prep. & training environment
1. Know how to wanggle data in a scale
1. Expermiments on data and select  
1. Deploy and interact with score model

## Briefing

Overview and intro about Azure Data Services
Focus on data preparation and machine learning experiments
demo
	* Databricks and ML Studio

## Hands on lab
Architecture and scenario

## Architecture
![overallarch](./images/arch01.01.png)

## Scenario

### Lab 00 Create hands on lab environment

1. Open browser and go to [Azure Portal](https://portal.azure.com)

1. Open cloud shell from the browser

1. Download a script

	```
	wget -O az-adv-analytics.azcli https://raw.githubusercontent.com/xlegend1024/az-cloudscale-adv-analytics/master/script/00.CreateLabEnv.azcli
	```

1. Run command to create a resource group and resource

> Care with subscription name when you run the script

![run script](./images/env01.01.png)

Make sure you use correct __Azure Subscription__ for the Hands-on lab.

1. Make sure you have a resource group and Azure Key Vault, Blob, SQLDB in the resource group
	
### Lab 01 Ingest

1. Create Azure Data Factory (v2)

1. Create Data Pipeline

	1. Create Connections HTTPs and Blob
	1. Create Datasets for both HTTPs and Blob
	1. Create Copy activity

### Lab 02 Data wrangling  

(Demo) Databricsk tour

1. Create Azure Databricks

1. Create Azure Databricks cluster

1. Import Notebook

	1. Import from  https://raw.githubusercontent.com/xlegend1024/az-cloudscale-adv-analytics/master/AzureDatabricks/02.datawrangling.ipynb

	1. Update widget parameters

	1. Run command from the notebook
	
		* Run differen languages (Python, Scala, R, SQL) to load data from blob to databricks
		* Data wrangling
		* Save final training dataset to blob

### Lab 03. Modeling

(Demo) Azure ML experiments

1. Create Azure Machine Learning Studio

1. Create workspace

Access the training dataset and import into Azure ML Studio.

### Lab 04. Operationalize score model

	(Demo) Azure ML operationalization
	Create web service
	Update inputs
	Publish web service
	Download a sample excel and test   

### Lab 05. Run

	(Demo) ADF and ML
	Create a new pipeline for batch ml processing
	

---

```bash
 dbutils.fs.put("dbfs:/databricks/init/init.bash" ,"""
 #!/bin/bash
 sudo echo export AZURE_STORAGE_CONNECTION_STRING="\\"DefaultEndpointsProtocol=https;AccountName=$myAccountName$;AccountKey=$myAccountKey$\\"" >> /databricks/spark/conf/spark-env.sh
 """, True)
 ```

---

## Sources and references
* https://docs.microsoft.com/en-us/azure/machine-learning/studio/azure-ml-customer-churn-scenario