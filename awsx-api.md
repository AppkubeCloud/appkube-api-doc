Provisioning --
AWSX --vaultURL=vault.synectiks.net --controlTowerArn="arn1" createLandingZone  -- landingZoneSpec = file1.json --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --LandingZoneId=636363636 createProductEnclave  -- productEnclaveSpec = file1.json --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --productEnclaveId=636363636 createCluster  -- clusterSpec = file1.json --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --clusterId=636363636 deployServiceInCluster  -- prod=EMS --env= PROD --serviceName = Admission 
--serviceType = business --serviceSpec = file1.json --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --productEnclaveId=636363636 deployServiceInCloudManaged  -- prod=EMS --env= PROD --serviceName = FileRepo --serviceType = common -- serviceSpec = file1.json --zone=us-west-2


AWSX --vaultURL=vault.synectiks.net --LandingZoneId=636363636  getElements  --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --LandingZoneId=636363636  getElementsMetadata  elementType=EKS  --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --accountId=636363636  getElementMetadata  elementType=EKS  elementId=id --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --accountId=636363636  getElementMetadata  elementType=APIGW --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --accountId=636363636  getElementMetadata  elementType=APIGW -- prod=EMS --env= PROD ----zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --accountId=636363636  getElementMetadata  elementType=WAF -- prod=EMS --env= PROD ----zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --accountId=636363636  getElementMetadata  elementType=Lambdas --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --accountId=636363636  getElementMetadata  elementType=Lambdas -- prod=EMS --env= PROD ----zone=us-west-2



AWSX --vaultURL=vault.synectiks.net --accountId=636363636  getLambdas -- prod=EMS --env= PROD --zone=us-west-2
AWSX --vaultURL=vault.synectiks.net getApiGw -- prod=EMS --env= PROD --zone=us-west-2 (find accountId from CMDB and then filter)
AWSX --vaultURL=vault.synectiks.net getWaf -- prod=EMS --env= PROD --zone=us-west-2 (find accountId from CMDB and then filter)

AWSX --vaultURL=vault.synectiks.net getLb -- prod=EMS --env= PROD --zone=us-west-2 (find accountId from CMDB and then filter)

AWSX --vaultURL=vault.synectiks.net getWafMetaData -- prod=EMS --env= PROD --zone=us-west-2 (find accountId from CMDB and then filter)

AWSX --vaultURL=vault.synectiks.net getApiGwMetaData -- prod=EMS --env= PROD --zone=us-west-2 (find accountId from CMDB and then filter and then get details metadata)

AWSX --vaultURL=vault.synectiks.net getLbMetaData -- prod=EMS --env= PROD --zone=us-west-2 (find accountId from CMDB and then filter and then get details metadata)

AWSX --vaultURL=vault.synectiks.net getClusterArn -- prod=EMS --env= PROD --zone=us-west-2 (find accountId from CMDB and then filter and then get details metadata)

AWSX --vaultURL=vault.synectiks.net getClusterMetaData -- prod=EMS --env= PROD --zone=us-west-2 (find accountId from CMDB and then filter and then get details metadata)

AWSX --vaultURL=vault.synectiks.net getServiceMeshURL -- prod=EMS --env= PROD --zone=us-west-2 (find accountId from CMDB and then filter and then get details metadata)

AWSX --vaultURL=vault.synectiks.net getServiceMeshMetaData -- prod=EMS --env= PROD --zone=us-west-2 (find accountId from CMDB and then filter and then get details metadata)


Cost Spike related CLI's

### Description--
This CLI will get the cost trends (up/down  for dialy / weekly / monthly ) for any App / Data services. We often need to filter the App and Data services based on (product / env / module ) and determine the consolidated cost trends.

Example -- 
    awsx cost getCostSpike --arn --account=646456546 --services=S3 --Product="EMS " --env="PROD" --Module="Admission" --period=daily/monthly/Hourly --start= "2/10/2023 " --end= "2/31/2023" (percentage wise ; bucket wise)

This should collect the daily cost data from 2/10/2023 to 2/31/2023 of those buckets that is used by EMS product , Prod Environment , Admission module and calculate the trends.

Algorithm:
    
    Find all the buckets that is used by product=EMS , ENV=PROD , MODULE=Admission

        Find the Cost of the corresponding buckets(sum) day-wise from 2/10/2023 to 2/31/2023

                {Total Volume of Buckets * Per Unit S3 cost}

        Get the data in the following format inside the program

            |Date | Cost | 
            |:---|:---|           
            |2/10/2023| 5.23|
            |2/11/2023| 5.83|   
            |2/12/2023| 5.95|


        Then calculate the difference and determine the spike  no and create another table as follows
            |Date | Cost | Spike | 
            |:---|:---|:---|
            |2/10/2023| 5.23|+10%|
            |2/11/2023| 5.83|+20%|   
            |2/12/2023| 5.95|+3%|
        Return this entire rows as suitable json or rows 

    
Example -- 
    awsx cost getCostSpike --arn --account=646456546 --services=EC2 --Product="EMS " --env="PROD" --Module="Admission" --period=daily/monthly/Hourly --start= "2/10/2023 " --end= "2/31/2023" (percentage wise ; instance name or ID wise, and the instance size)

This should collect the daily cost data from 2/10/2023 to 2/31/2023 of those instances that is used by EMS product , Prod Environment , Admission module and calculate the trends.

Algorithm:
    
    Find all the instances that is used by product=EMS , ENV=PROD , MODULE=Admission

        Find the Cost of the instances(sum) day-wise from 2/10/2023 to 2/31/2023

                {Total instances with their size and shall get cost for each instance}

        Get the data in the following format inside the program

            |Date | Cost | 
            |:---|:---|           
            |2/10/2023| 5.23|
            |2/11/2023| 5.83|   
            |2/12/2023| 5.95|


        Then calculate the difference and determine the spike now and create another table as follows
            |Date | Cost | Spike | 
            |:---|:---|:---|
            |2/10/2023| 5.23|+10%|
            |2/11/2023| 5.83|+20%|   
            |2/12/2023| 5.95|+3%|
        Return this entire rows as suitable json or rows


Example -- 
    awsx cost getCostSpike --arn --account=646456546 --services=EKS --Product="EMS " --env="PROD" --Module="Admission" --period=daily/monthly/Hourly --start= "2/10/2023 " --end= "2/31/2023" (percentage wise ; Cluster Name)

This should collect the daily cost data from 2/10/2023 to 2/31/2023 of those clusters that is used by EMS product , Prod Environment , Admission module and calculate the trends.

Algorithm:
    
    Find all the clusters that is used by product=EMS , ENV=PROD , MODULE=Admission

        Find the Cost of the clusters(sum) day-wise from 2/10/2023 to 2/31/2023

                {get billing for each cluster}

        Get the data in the following format inside the program

            |Date | Cost | 
            |:---|:---|           
            |2/10/2023| 5.23|
            |2/11/2023| 5.83|   
            |2/12/2023| 5.95|


        Then calculate the difference and determine the spike now and create another table as follows
            |Date | Cost | Spike | 
            |:---|:---|:---|
            |2/10/2023| 5.23|+10%|
            |2/11/2023| 5.83|+20%|   
            |2/12/2023| 5.95|+3%|
        Return this entire rows as suitable json or rows


Example -- 
    awsx cost getCostSpike --arn --account=646456546 --services=lambda --Product="EMS " --env="PROD" --Module="Admission" --period=daily/monthly/Hourly --start= "2/10/2023 " --end= "2/31/2023" (percentage wise ; function Name)

This should collect the daily cost data from 2/10/2023 to 2/31/2023 of those lambda functions that is used by EMS product , Prod Environment , Admission module and calculate the trends.

Algorithm:
    
    Fetch the lambda functions that is used by product=EMS , ENV=PROD , MODULE=Admission

        Find the Cost of the lamdba functions(sum) day-wise from 2/10/2023 to 2/31/2023

                {get billing for each lambda function(with_Name)}

        Get the data in the following format inside the program

            |Date | Cost | 
            |:---|:---|           
            |2/10/2023| 5.23|
            |2/11/2023| 5.83|   
            |2/12/2023| 5.95|


        Then calculate the difference and determine the spike now and create another table as follows
            |Date | Cost | Spike | 
            |:---|:---|:---|
            |2/10/2023| 5.23|+10%|
            |2/11/2023| 5.83|+20%|   
            |2/12/2023| 5.95|+3%|
        Return this entire rows as suitable json or rows


Example -- 
    awsx cost getCostSpike --arn --account=646456546 --services=RDS --Product="EMS " --env="PROD" --Module="Admission" --period=daily/monthly/Hourly --start= "2/10/2023 " --end= "2/31/2023" (percentage wise ; DataBase Name)

This should collect the daily cost data from 2/10/2023 to 2/31/2023 of those DB's that is used by EMS product , Prod Environment , Admission module and calculate the trends.

Algorithm:
    
    Find all the DB's that is used by product=EMS , ENV=PROD , MODULE=Admission

        Find the Cost of the DB's(sum) day-wise from 2/10/2023 to 2/31/2023

                {get billing for each DB and return their instance size which are attached to the DB's}

        Get the data in the following format inside the program

            |Date | Cost | 
            |:---|:---|           
            |2/10/2023| 5.23|
            |2/11/2023| 5.83|   
            |2/12/2023| 5.95|


        Then calculate the difference and determine the spike now and create another table as follows
            |Date | Cost | Spike | 
            |:---|:---|:---|
            |2/10/2023| 5.23|+10%|
            |2/11/2023| 5.83|+20%|   
            |2/12/2023| 5.95|+3%|
        Return this entire rows as suitable json or rows





