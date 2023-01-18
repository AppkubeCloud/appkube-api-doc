Provisioning --
AWSX --vaultURL=vault.synectiks.net --controlTowerArn="arn1" createLandingZone  -- landingZoneSpec = file1.json --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --LandingZoneId=636363636 createProductEnclave  -- productEnclaveSpec = file1.json --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --productEnclaveId=636363636 createCluster  -- clusterSpec = file1.json --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --clusterId=636363636 deployServiceInCluster  -- prod=EMS --env= PROD --serviceName = Admission 
--serviceType = business --serviceSpec = file1.json --zone=us-west-2

AWSX --vaultURL=vault.synectiks.net --productEnclaveId=636363636 deployServiceInCloudManaged  -- prod=EMS --env= PROD --serviceName = FileRepo 
--serviceType = common -- serviceSpec = file1.json --zone=us-west-2


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



