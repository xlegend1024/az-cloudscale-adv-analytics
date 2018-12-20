# Azure Data Factory using Azure Databricks for prediction

## 0. Setup Lab environment

Run follong comand from cloud shell

```bash
subName=
rgName=
loc=
```

```bash
az account set --subscription "$subName"
num=$(shuf -i0-1000 -n1)
blobName=azlab$num
containerName=sampledata
objName=customerchurnsource.csv
file_to_upload='./'$objName
az storage account create --name $blobName --resource-group $rgName --sku Standard_LRS --location $loc --kind StorageV2 
blobConn=$(az storage account show-connection-string --name $blobName --resource-group $rgName --output tsv)
az storage container create --name $containerName --connection-string $blobConn
wget -O $file_to_upload https://github.com/xlegend1024/az-cloudscale-adv-analytics/raw/master/sampledata/customerchurnsource.csv
az storage blob upload --container-name $containerName --file $file_to_upload --name $objName --connection-string $blobConn
```

## 1. Create Azure Databricks

1.1 Create ADB

1.2 Import notebookto user workspace

Import following notebook

```
https://github.com/xlegend1024/az-cloudscale-adv-analytics/blob/master/AzureDatabricks/score.ipynb
```

1.3 Generate token

Kepp your token safe

## 2. Create Azure Data Factory 

2.1 Create ADF

2.2 Import ADF Template

Download ARM template to import ADF pipeline

You need folling information

|Key|Value|
|---|---|
|Resource Group Name||
|ADF Name||
|ADB Token||

2.3 Update parameters and pipeline

|Name|value|
|---|---|
|STORAGE_ACCOUNT||
|ACCOUNT_KEY||
|CONTAINER||
|ML_PATH|wasbs://models@azureailabs.blob.core.windows.net/churn_classifier|

2.4 Run the pipeline and see result