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
|departments|GET | /organizations/{orgId}/departments | | [Response JSON](./jsons/Department/all.json)|
|products|GET | /organizations/{orgId}/products | | |
|landing Zones |GET | /organizations/{orgId}/landing-zone | | |
|product enclaves|GET | /organizations/{orgId}/product-enclave | | |
|resource count|GET | /organizations/{orgId}/cloud-environments/count | | |
|resource summary|GET | /organizations/{orgId}/cloud-environments/summary | | |
|services |GET | /organizations/{orgId}/services | | |

#### **2. organization and department wise**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|products|GET | /organizations/{orgId}/departments/{depId}/products | | |
|landing-zone |GET | /organizations/{orgId}/departments/{depId}/landing-zone | | | 
|product enclave |GET | /organizations/{orgId}/departments/{depId}/product-enclave | | |
|services |GET | /organizations/{orgId}/departments/{depId}/services | | |

#### **3. organization and products wise services**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services products |GET | /organizations/{orgId}/products/{product}/services | | |
#### **4. organization and environments wise services**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services environments |GET | /organizations/{orgId}/environments/{env}/services | | |
#### **6. organization and products and environments wise services**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services products environments |GET | /organizations/{orgId}/products/{product}/environments/{env}/services | | |
#### **7. organization and service wise**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services service-type |GET | /organizations/{orgId}/service-type/{serviceType}/services | | |
|services service-cost |GET | /organizations/{orgId}/services/{serviceName}/service-cost | | |
|services service-daily-cost |GET | /organizations/{orgId}/services/{serviceName}/service-cost/daily | | |
|services service-weekly-cost |GET | /organizations/{orgId}/services/{serviceName}/service-cost/weekly | | |
|services service-monthly-cost |GET | /organizations/{orgId}/services/{serviceName}/service-cost/monthly | | |
#### **8. organization and landingZone  wise service**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services service-landing-zone-services-name |GET | /organizations/{orgId}/landing-zone/{landingZone}/services | | |
|services service-landing-zone-products |GET | /organizations/{orgId}/landing-zone/{landingZone}/products | | |
#### **9. organization and service wise service-sla**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services service-sla |GET | /organizations/{orgId}/services/{name}/service-sla | | |
|services service-cureent-sla |GET | /organizations/{orgId}/services/{serviceName}/service/cureent-sla | | |
|services service-weekly-sla |GET | /organizations/{orgId}/services/{serviceName}/service/weekly-sla | | |
|services service-monthly-sla |GET | /organizations/{orgId}/services/{serviceName}/service/monthly-sla | | |
#### **10. organization and department and products wise service**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services products |GET | /organizations/{orgId}/departments/{depId}/products/{product}/services | | |
#### **11. organization and department and products and environments wise service**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---| 
|services environments |GET | /organizations/{orgId}/departments/{depId}/environments/{env}/services | | |
|services products environments |GET | /organizations/{orgId}/departments/{depId}/products/{product}/environments/{env}/services | | |
#### **12. organization and department  wise service**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---| 
|services service-type |GET | /organizations/{orgId}/departments/{depId}/service-type/{serviceType}/services | | |
|services service-cost |GET | /organizations/{orgId}/departments/{depId}/services/{serviceName}/service-cost | | |
|services service-daily-cost |GET | /organizations/{orgId}/departments/{depId}/services/{serviceName}/service-cost/daily | | |
|services service-weekly-cost |GET | /organizations/{orgId}/departments/{depId}/services/{serviceName}/service-cost/weekly | | |
|services service-monthly-cost |GET | /organizations/{orgId}/departments/{depId}/services/{serviceName}/service-cost/monthly | | |
#### **13. organization and department landingZone  and service wise**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---|
|services service-landing-zone-services-name |GET | /organizations/{orgId}/departments/{depId}/landing-zone/{landingZone}/services | | |
|services service-landing-zone-products |GET | /organizations/{orgId}/departments/{depId}/landing-zone/{landingZone}/products | | |
#### **14. organization and department and service wise service-sla**
| description | method | end point | Request | Response | 
|:---|:---|:---|:---|:---| 
|services service-sla |GET | /organizations/{orgId}/departments/{depId}/services/{name}/service-sla | | |
|services service-cureent-sla |GET | /organizations/{orgId}/departments/{depId}/services/{serviceName}/service/cureent-sla | | |
|services service-weekly-sla |GET | /organizations/{orgId}/departments/{depId}/services/{serviceName}/service/weekly-sla | | |
|services service-monthly-sla |GET | /organizations/{orgId}/departments/{depId}/services/{serviceName}/service/monthly-sla | | |
