# 05. Run Azure ML in Batch

## Architecture

## 0. Access to Azure Portal

Go to [Azure Portal](https://azure.portal.com) for lab.

## 1. Open ADF 'Author & Monitor'

## 2. Create Connection

![new connection](./images/05.01.png)

![new connection](./images/05.02.png)

![new connection](./images/05.03.png)

![new connection](./images/05.04.png)

![new connection](./images/05.05.png)

![new connection](./images/05.06.png)


## 3. Create Dataset

![new connection](./images/05.08.png)

```sql
SELECT 
age,
annualincome,
calldroprate,
callfailurerate, 
callingnum,
customerid,
customersuspended,
gender,
homeowner,
maritalstatus,
monthlybilledamount,
numberofcomplaints,
numberofmonthunpaid,
numdayscontractequipmentplanexpiring,
occupation,
penaltytoswitch,
[state],
totalminsusedinlastmonth,  
unpaidbalance, 
usesinternetservice, 
usesvoiceservice,
percentagecalloutsidenetwork,
totalcallduration, 
avgcallduration
FROM tblCustomers
```

![new connection](./images/05.08.01.png)

customer_stg

stage/sqldb_tblcustomers.csv

![new connection](./images/05.08.02.png)

![new connection](./images/05.09.png)

![new connection](./images/05.10.png)

![new connection](./images/05.11.png)

![new connection](./images/05.12.png)

![new connection](./images/05.13.png)

---
[Next > 99. Clean Up](https://github.com/xlegend1024/az-cloudscale-adv-analytics/blob/master/99Cleanup.md)

---
[Main](https://github.com/xlegend1024/az-cloudscale-adv-analytics/blob/master/README.md)
