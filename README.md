# Cloud Scale Advanced Analtyics

Experience end-to-end Advanced Analytics on cloud using Blob, ADF, Databricks, SQLDB/DW and Azure Machine Leaning Studio.

Thu out this hands on lab Understand how to apply followings for you work:

* ADF
* Databricks
* SQLDB
* Azure ML Studio

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

### Architecture
![overallarch](./images/arch01.01.png)

### Scenario

Lab 00 Create hands on lab environment

	Click link to create lab environment

	Make sure you have a resource group and Azure Key Vault, Blob, SQLDB in the resource group

		Restore SQL DB from SQLDB backup

	
Lab 01 Ingest

	Create ADF

		Create Connections HTTPs and Blob
		Create Datasets for both HTTPs and Blob
		Create Copy activity

Lab 02 Data wrangling  

	(Demo) Databricsk tour
	Create Azure Databricks
	Import notebook from (https://raw.githubusercontent.com/xlegend1024/az-cloudscale-adv-analytics/master/AzureDatabricks/02.datawrangling.ipynb)
	Update widget parameters 
	Run differen languages (Python, Scala, R, SQL) to load data from blob to databricks
	Data wrangling
	Save final training dataset to blob

Lab 03. Modeling

	(Demo) Azure ML experiments
	Access the training dataset and import into Azure ML Studio

Lab 04. Operationalize score model

	(Demo) Azure ML operationalization
	Create web service
	Update inputs
	Publish web service
	Download a sample excel and test   

Lab 05. Run

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