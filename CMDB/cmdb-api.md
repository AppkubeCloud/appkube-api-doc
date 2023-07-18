# Release 0.0.0.1
## CMDB APIs 
### Base API : http://34.199.12.114:6057/api
### 1. [CURD API End Points](./md-files/cmd-curd-apis.md)
| Entity | API End Point Document | 
|:---|:---|
|Organization | [URL](https://github.com/AppkubeCloud/appkube-architectures/blob/main/md-files/cmd-curd-apis.md#organization) |
|Department | [URL](https://github.com/AppkubeCloud/appkube-architectures/blob/main/md-files/cmd-curd-apis.md#department) |
|Cloud Environment (Landing Zone) | [URL](https://github.com/AppkubeCloud/appkube-architectures/blob/main/md-files/cmd-curd-apis.md#cloud-environment) |
|Cloud Element Summary | [URL](https://github.com/AppkubeCloud/appkube-architectures/blob/main/md-files/cmd-curd-apis.md#cloud-element-summary) |
|Cloud Element | [URL](https://github.com/AppkubeCloud/appkube-architectures/blob/main/md-files/cmd-curd-apis.md#cloud-element) |
|Micro Service | [URL](https://github.com/AppkubeCloud/appkube-architectures/blob/main/md-files/cmd-curd-apis.md#micro-service) |
|Deployment Environment | [URL](https://github.com/AppkubeCloud/appkube-architectures/blob/main/md-files/cmd-curd-apis.md#deployment-environment) |
|Catalogue | [URL](https://github.com/AppkubeCloud/appkube-architectures/blob/main/md-files/cmd-curd-apis.md#catalogue) |

### Query API End Points
#### **1. organization wise**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|departments|GET |/query /organizations/{orgId}/departments | | [Response JSON](./jsons/Department/all.json)|
|products|GET | /query/organizations/{orgId}/products | | |
|landing Zones |GET | /query/organizations/{orgId}/landing-zone | | |
|product enclaves|GET | /query/organizations/{orgId}/product-enclave | | |
|resource count|GET | /query/organizations/{orgId}/cloud-environments/count | | |
|resource summary|GET | /query/organizations/{orgId}/cloud-environments/summary | | |
|services |GET | /query/organizations/{orgId}/services | | |
#### **2. organization and department wise**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|products|GET | /query/organizations/{orgId}/departments/{depId}/products | | |
|landing-zone |GET | /query/organizations/{orgId}/departments/{depId}/landing-zone | | | 
|product enclave |GET | /query/organizations/{orgId}/departments/{depId}/product-enclave | | |
|services |GET | /query/organizations/{orgId}/departments/{depId}/services | | |

#### **3. organization and products wise services**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services products |GET | /query/organizations/{orgId}/products/{product}/services | | |

#### **4. organization and environments wise services**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services environments |GET | /query/organizations/{orgId}/environments/{env}/services | | |
#### **5. organization and products and environments wise services**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services products environments |GET | /query/organizations/{orgId}/products/{product}/environments/{env}/services | | |
#### **6. organization and service wise**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services service-type |GET | /query/organizations/{orgId}/service-type/{serviceType}/services | | |
|services service-cost |GET | /query/organizations/{orgId}/services/{serviceName}/service-cost | | |
|services service-daily-cost |GET | /query/organizations/{orgId}/services/{serviceName}/service-cost/daily | | |
|services service-weekly-cost |GET | /query/organizations/{orgId}/services/{serviceName}/service-cost/weekly | | |
|services service-monthly-cost |GET | /query/organizations/{orgId}/services/{serviceName}/service-cost/monthly | | |
#### **7. organization and landingZone  wise service**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services service-landing-zone-services-name |GET | /query/organizations/{orgId}/landing-zone/{landingZone}/services | | |
|services service-landing-zone-products |GET | /query/organizations/{orgId}/landing-zone/{landingZone}/products | | |
|services service-landing-zone-product-enclave |GET | /query/organizations/{orgId}/landing-zone/{landingZone}/product-enclave | | |
|landing zone infra topology |GET | /query/organizations/{orgId}/landing-zone/{landingZone}/infra-topology | | |
#### **8. organization and service wise service-sla**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services service-sla |GET | /query/organizations/{orgId}/services/{name}/service-sla | | |
|services service-cureent-sla |GET | /query/organizations/{orgId}/services/{serviceName}/service/cureent-sla | | |
|services service-weekly-sla |GET | /query/organizations/{orgId}/services/{serviceName}/service/weekly-sla | | |
|services service-monthly-sla |GET | /query/organizations/{orgId}/services/{serviceName}/service/monthly-sla | | |
#### **9. organization and department and products wise service**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services products |GET | /query/organizations/{orgId}/departments/{depId}/products/{product}/services | | |
#### **10. organization and department and products and environments wise service**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---| 
|services environments |GET | /query/organizations/{orgId}/departments/{depId}/environments/{env}/services | | |
|services products environments |GET | /query/organizations/{orgId}/departments/{depId}/products/{product}/environments/{env}/services | | |
#### **12. organization and department  wise service**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---| 
|services service-type |GET | /query/organizations/{orgId}/departments/{depId}/service-type/{serviceType}/services | | |
|services service-cost |GET | /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service-cost | | |
|services service-daily-cost |GET | /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service-cost/daily | | |
|services service-weekly-cost |GET | /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service-cost/weekly | | |
|services service-monthly-cost |GET | /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service-cost/monthly | | |
#### **13. organization and department landingZone  and service wise**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services service-landing-zone-services-name |GET | /query/organizations/{orgId}/departments/{depId}/landing-zone/{landingZone}/services | | |
|services service-landing-zone-products |GET | /query/organizations/{orgId}/departments/{depId}/landing-zone/{landingZone}/products | | |
|services service-landing-zone-product-enclave |GET | /query/organizations/{orgId}/departments/{depId}/landing-zone/{landingZone}/product-enclave | | |
#### **14. organization and department and service wise service-sla**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---| 
|services service-sla |GET | /query/organizations/{orgId}/departments/{depId}/services/{name}/service-sla | | |
|services service-cureent-sla |GET | /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service/cureent-sla | | |
|services service-weekly-sla |GET | /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service/weekly-sla | | |
|services service-monthly-sla |GET | /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service/monthly-sla | | |
#### **15. organization and cloud wise**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|resource count|GET | /query/organizations/{orgId}/cloud/{cloud}/cloud-environments/count | | |
|resource summary|GET | /query/organizations/{orgId}/cloud/{cloud}/cloud-environments/summary | | |
#### **16. organization and landingZone and cloud wise**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|resource count|GET | /query/organizations/{orgId}/cloud/{cloud}/landingZone/{landingZone}/cloud-environments/count | | |
#### **17. organization and landingZone and product wise**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|vpc summary|GET | /query/organizations/{orgId}/landing-zone/{landingZone}/product-enclave/{product}/vpc-summary | | |
|infra topology summary|GET | |vpc summary|GET |  /query/organizations/{orgId}/landing-zone/{landingZone}/product-enclave/{productEnclave}/infra-topology-summary | | | 

#### **18. organization wise spend analytics**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|spend today |GET |/query/organizations/{orgId}/analytics/spend-analytics/spend-today| | |
|spend yesterday|GET | /query/organizations/{orgId}/analytics/spend-analytics/spend-yesterday | | |
|avg per hour |GET | /query/organizations/{orgId}/analytics/spend-analytics/spend-current-rate/avg-per-hour | | |
|per day|GET | /query/organizations/{orgId}/analytics/spend-analytics/spend-current-rate/per-day | | |
|spend total|GET | /query/organizations/{orgId}/analytics/spend-analytics/spend-total | | |
|cloud wise spend|GET | /query/organizations/{orgId}/analytics/spend-analytics/cloud-wise-spend | | |
|monthly cloud wise spend |GET | /query/organizations/{orgId}/analytics/spend-analytics/monthly-cloud-wise-spend | | |
|monthly statistics |GET | /query/organizations/{orgId}/analytics/spend-analytics/monthly-statistics | | |
|total-budget |GET | /query/organizations/{orgId}/analytics/spend-analytics/total-budget | | |
#### **19. organization wise cost analytics**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|product wise cost  |GET | /query/organizations/{orgId}/analytics/cost-analytics/product-wise-cost | | |
|production vs others|GET | /query/organizations/{orgId}/analytics/cost-analytics/production-vs-others | | |
|service type wise cost |GET | /query/organizations/{orgId}/analytics/cost-analytics/service-type-wise-cost | | |
#### **20. organization wise billing**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|organizations wise billing  |GET | /query/organizations/{orgId}/billing/cloud-element/entity/{entity}/organizations-wise-billing | | |
|element wise billing |GET | /query/organizations/{orgId}/billing/cloud-element/entity/{entity}/element-name/{elementName}/element-wise-billing | | |
|landingzone wise billing |GET | /query/organizations/{orgId}/billing/cloud-element/entity/{entity}/landingzone/{landingZone}/landingzone-wise-billing | | |
|landingzone element wise billing |GET | /query/organizations/{orgId}/billing/cloud-element/element-name/entity/{entity}/{elementName}/landingzone/{landingZone}/landingzone-element-wise-billing  | | | 