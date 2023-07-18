### `CMDB Port: 6057`
### `1. organization wise products`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/products
Request - Path variable {orgId}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getProduct(@Param("orgId") Long orgId);
		4.1 This getProduct method accepts long type organization id and pass it to the native sql
		4.2 Native sql returns the list of products (List<String>) of the given organization id
	5. JPA repository returns this list of products to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `1.1 organization wise landing Zones`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/landing-zone
Request - Path variable {orgId}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getLandingZones(@Param("orgId") Long orgId);
        4.1 This getLandingZones method accepts long type organization id and pass it to the native sql
		4.2 Native sql returns the list of landing zone (List<String>) of the given organization id
	5. JPA repository returns this list of landing zone to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `1.2 organization wise product enclaves`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/product-enclave
Request - Path variable {orgId}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getOrganizationProductEnclave(@Param("orgId") Long orgId);
        4.1 This getOrganizationProductEnclave method accepts long type organization id and pass it to the native sql
		4.2 Native sql returns the list of product enclaves (List<String>) of the given organization id
	5. JPA repository returns this list of product enclaves to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>


### `1.3 organization wise environment resource counts`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/cloud-environments/count
Request - Path variable {orgId}
Response - List<EnvironmentCountsDto>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<EnvironmentCountsDto> getCount(@Param("orgId") Long orgId);
        4.1 This getCount method accepts long type organization id and pass it to the native sql
		4.2 Native sql returns the list of landing zone (List<EnvironmentCountsDto>) of the given organization id
	5. JPA repository returns this list of landing zone to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `1.4 organization wise list of landing zone and its associated product enclaves, products, app and data services`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/cloud-environments/summary
Request - Path variable {orgId}
Response - List<EnvironmentDto>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<EnvironmentCountsDto> getEnvironmentSummary(@Param("orgId") Long orgId);
        4.1 This getEnvironmentSummary method accepts long type organization id and pass it to the native sql
		4.2 Native sql returns the list of landing zone (List<EnvironmentCountsDto>) Filter list cloud wise in service class. 
		4.3 Service returns the list of landing zone (List<EnvironmentCountsDto>) of the given organization id
	5. JPA repository returns this list of landing zone to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `1.5. organization wise departments`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments
Request - Path variable {orgId}
Response - Set<Department>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. JPA repository returns this list of department to service class and service class returns the same list to contorller then get department from the list and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `1.6. organization wise  services`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/services
Request - Path variable {orgId}
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationMicroServices(@Param("orgId") Long orgId);
		4.1 This getOrganizationMicroServices method accepts long type organization id and pass it to the native sql
		4.2 Native sql returns the list of services (List<object>) of the given organization id
	5. JPA repository returns this list of services to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>


### `2.organization and department wise products`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/products	
Request - Path variable {orgId} , Path variable {depId}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getDepartmentProducts(@Param("orgId") Long orgId, @Param("depId") Long depId);
        4.1 This getDepartmentProducts method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  products of an department an Organization (List<String>) of the given organization id and department id
	5. JPA repository returns this list of  products of an department an Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `2.1.organization and department wise landing Zones`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/landing-zone
Request - Path variable {orgId} , Path variable {depId}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getDepartmentLandingZones(@Param("orgId") Long orgId , @Param("depId") Long depId);
        4.1 This getDepartmentLandingZones method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  landing zone of an department an Organization (List<String>) of the given organization id and department id
	5. JPA repository returns this list of  landing zone of an department an Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `2.2.organization and department wise product enclaves`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/product-enclave
Request - Path variable {orgId} , Path variable {depId}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getOrganizationDepartmentsProductEnclave(@Param("orgId") Long orgId , @Param("depId") Long depId);
        4.1 This getOrganizationDepartmentsProductEnclave method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  product enclaves of an department an Organization (List<String>) of the given organization id and department id
	5. JPA repository returns this list of  product enclaves of an department an Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>



### `2.3.organization and department wise  services`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/services
Request - Path variable {orgId} , Path variable {depId}
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationDepartmentsMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId);
        4.1 This getOrganizationDepartmentsMicroServices method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  services of an department an Organization (List<object>) of the given organization id and department id
	5. JPA repository returns this list of  services of an department an Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>


### `3. organization and products wise services`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/products/{product}/services
Request - Path variable {orgId} , Path variable {product}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getOrganizationproductsMicroServices(@Param("orgId") Long orgId,@Param("product") String product);
		4.1 This getOrganizationproductsMicroServices method accepts long type organization id and product pass it to the native sql
		4.2 Native sql returns the list of services (List<String>) of the given organization id and product
	5. JPA repository returns this list of services to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `4. organization wise services environments`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/environments/{env}/services
Request - Path variable {orgId} , Path variable {env}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getOrganizationEnvMicroServices(@Param("orgId") Long orgId,@Param("env") Long env);
		4.1 This getOrganizationEnvMicroServices method accepts long type organization id and env pass it to the native sql
		4.2 Native sql returns the list of services (List<String>) of the given organization id and env
	5. JPA repository returns this list of services to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>


### `5. organization wise services environments`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/products/{product}/environments/{env}/services
Request - Path variable {orgId},  Path variable {product} , Path variable {env}
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationProductEnvMicroServices(@Param("orgId") Long orgId,@Param("product") String product,@Param("env") Long env);
		4.1 This getOrganizationProductEnvMicroServices method accepts long type organization id and env and product pass it to the native sql
		4.2 Native sql returns the list of services (List<object>) of the given organization id and env and product
	5. JPA repository returns this list of services to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `6. organization and service wise`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/service-type/{serviceType}/services
Request - Path variable {orgId}, Path variable {serviceType} 
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getOrganizationServiceTypeMicroServices(@Param("orgId") Long orgId,@Param("serviceType") String serviceType);
		4.1 This getOrganizationServiceTypeMicroServices method accepts long type organization id and serviceType pass it to the native sql
		4.2 Native sql returns the list of services (List<String>) of the given organization id and serviceType
	5. JPA repository returns this list of services to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `6.1. organization wise services service-cost`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/services/{serviceName}/service-cost
Request - Path variable {orgId}, Path variable {serviceName} 
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationServiceNameMicroServices(@Param("orgId") Long orgId,@Param("serviceName") String serviceName);
		4.1 This getOrganizationServiceNameMicroServices method accepts long type organization id and serviceName pass it to the native sql
		4.2 Native sql returns the list of services-cost (List<object>) of the given organization id and serviceName
	5. JPA repository returns this list of services-cost to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client
<hr>


### `6.2. organization wise services service-cost-daily`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/services/{serviceName}/service-cost/daily
Request - Path variable {orgId}, Path variable {serviceName} 
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationServiceNameDailyMicroServices(@Param("orgId") Long orgId,@Param("serviceName") String serviceName);
		4.1 This getOrganizationServiceNameDailyMicroServices method accepts long type organization id and serviceName pass it to the native sql
		4.2 Native sql returns the list of services-cost (List<object>) of the given organization id and serviceName
	5. JPA repository returns this list of services-cost to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client
<hr>

### `6.3. organization wise services service-cost-weekly`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/services/{serviceName}/service-cost/weekly
Request - Path variable {orgId}, Path variable {serviceName} 
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationServiceNameWeeklyMicroServices(@Param("orgId") Long orgId,@Param("serviceName") String serviceName);
		4.1 This getOrganizationServiceNameWeeklyMicroServices method accepts long type organization id and serviceName pass it to the native sql
		4.2 Native sql returns the list of services-cost (List<object>) of the given organization id and serviceName
	5. JPA repository returns this list of services-cost to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client
<hr>

### `6.4. organization wise services service-cost-monthly`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/services/{serviceName}/service-cost/monthly
Request - Path variable {orgId}, Path variable {serviceType} 
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationServiceNameMonthlyMicroServices(@Param("orgId") Long orgId,@Param("serviceName") String serviceName);
		4.1 This getOrganizationServiceNameMonthlyMicroServices method accepts long type organization id and serviceName pass it to the native sql
		4.2 Native sql returns the list of services-cost (List<object>) of the given organization id and serviceName
	5. JPA repository returns this list of services-cost to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client
<hr>


### `7.organization and landingZone  wise service `
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/landing-zone/{landingZone}/services
Request - Path variable {orgId}, Path variable {landingZone} 
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getOrganizationLandingZoneMicroServices(@Param("orgId") Long orgId,@Param("landingZone") String landingZone);
		4.1 This getOrganizationLandingZoneMicroServices method accepts long type organization id and landingZone pass it to the native sql
		4.2 Native sql returns the list of services (List<String>) of the given organization id and landingZone
	5. JPA repository returns this list of services to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client
<hr>

### `7.1. organization wise services service-landing-zone-services-products`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/landing-zone/{landingZone}/products
Request - Path variable {orgId}, Path variable {landingZone} 
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getOrganizationProductsMicroServices(@Param("orgId") Long orgId,@Param("landingZone") String landingZone);
		4.1 This getOrganizationProductsMicroServices method accepts long type organization id and landingZone pass it to the native sql
		4.2 Native sql returns the list of services (List<String>) of the given organization id and landingZone
	5. JPA repository returns this list of services to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client
<hr>

### `8.organization and service wise service-sla `

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/services/{name}/service-sla
Request - Path variable {orgId}, Path variable {name} 
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationServiceSlaMicroServices(@Param("orgId") Long orgId,@Param("serviceName") String serviceName);
		4.1 This getOrganizationServiceSlaMicroServices method accepts long type organization id and serviceName pass it to the native sql
		4.2 Native sql returns the list of services-sla (List<object>) of the given organization id and serviceName
	5. JPA repository returns this list of services-sla to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client
<hr>


### `8.1. organization wise services service-cureent-sla`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/services/{serviceName}/service/cureent-sla
Request - Path variable {orgId}, Path variable {serviceName} 
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationServiceCurrentSlaMicroServices(@Param("orgId") Long orgId,@Param("serviceName") String serviceName);
		4.1 This getOrganizationServiceCurrentSlaMicroServices method accepts long type organization id and serviceName pass it to the native sql
		4.2 Native sql returns the list of services-current-sla (List<object>) of the given organization id and serviceName
	5. JPA repository returns this list of services-current-sla to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client
<hr>

### `8.2. organization wise services service-weekly-sla`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/services/{serviceName}/service/weekly-sla
Request - Path variable {orgId}, Path variable {serviceName} 
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationServiceWeeklySlaMicroServices(@Param("orgId") Long orgId,@Param("serviceName") String serviceName);
		4.1 This getOrganizationServiceWeeklySlaMicroServices method accepts long type organization id and serviceName pass it to the native sql
		4.2 Native sql returns the list of services-weekly-sla (List<object>) of the given organization id and serviceName
	5. JPA repository returns this list of services-weekly-sla to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client
<hr>

### `8.3. organization wise services service-monthly-sla`

```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/services/{serviceName}/service/monthly-sla
Request - Path variable {orgId}, Path variable {serviceName} 
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationServiceMonthlySlaMicroServices(@Param("orgId") Long orgId,@Param("serviceName") String serviceName);
		4.1 This getOrganizationServiceMonthlySlaMicroServices method accepts long type organization id and serviceName pass it to the native sql
		4.2 Native sql returns the list of services-monthly-sla (List<object>) of the given organization id and serviceName
	5. JPA repository returns this list of services-monthly-sla to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client
<hr>

### `9.organization and department and products wise service `
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/products/{product}/services
Request - Path variable {orgId} , Path variable {depId} ,Path Variable  product
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationDepartmentsProductMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("product") String product);
        4.1 This getOrganizationDepartmentsProductMicroServices method accepts long type organization id and long type department id and product pass it to the native sql
		4.2 Native sql returns the list of  services of an department an Organization (List<object>) of the given organization id and department id and product
	5. JPA repository returns this list of  services of an department an Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `10.organization and department and products and environments wise service `
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/environments/{env}/services
Request - Path variable {orgId} , Path variable {depId} ,Path Variable {env}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getOrganizationDepartmentsEnvMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("env") Long env);
        4.1 This getOrganizationDepartmentsEnvMicroServices method accepts long type organization id and long type department id and env pass it to the native sql
		4.2 Native sql returns the list of  services of an department an Organization (List<String>) of the given organization id and department id and env
	5. JPA repository returns this list of  services of an department an Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `11.organization and cloud wise landing Zones `
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/cloud/{cloudName}/landing-zone	
Request - Path variable {orgId} , Path variable {cloudName}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getCloudnameLandingZones(@Param("orgId") Long orgId, @Param("cloudName") String cloudName );
        4.1 This getCloudnameLandingZones method accepts long type organization id and string type cloudName  and pass it to the native sql
		4.2 Native sql returns the list of  landing Zones  of an cloudName an Organization (List<String>) of the given organization id and cloudName 
	5. JPA repository returns this list of  landing Zones  of an cloudName an Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `11.1.organization and department wise services products environments`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/products/{product}/environments/{env}/services
Request - Path variable {orgId} , Path variable {depId},Path Variable {product} ,Path Variable {env}
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationDepartmentsProductEnvMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("env") Long product,@Param("env") Long env);
        4.1 This getOrganizationDepartmentsProductEnvMicroServices method accepts long type organization id and long type department id and env and product pass it to the native sql
		4.2 Native sql returns the list of  services of an department an Organization (List<object>) of the given organization id and department id and env and product
	5. JPA repository returns this list of  services of an department an Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>


### `12.organization and department  wise service`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/service-type/{serviceType}/services
Request - Path variable {orgId} , Path variable {depId} ,Path Variable  {serviceType}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getOrganizationDepartmentsServiceTypeMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("serviceType") String serviceType);
        4.1 This getOrganizationDepartmentsServiceTypeMicroServices method accepts long type organization id and long type department id and serviceType pass it to the native sql
		4.2 Native sql returns the list of  services of an department an Organization (List<String>) of the given organization id and department id and serviceType
	5. JPA repository returns this list of  services of an department an Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>


### `12.1.organization and department wise service-cost`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service-cost
Request - Path variable {orgId} , Path variable {depId} , Path variable {serviceName}
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationDepartmentsServiceNameMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("serviceName") String serviceName);
        4.1 This getOrganizationDepartmentsServiceNameMicroServices method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  service-cost of an department an serviceName an Organization (List<object>) of the given organization id and department id and service-name
	5. JPA repository returns this list of  service-cost of an department an serviceName  Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `12.2.organization and department wise service-cost-daily`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service-cost/daily
Request - Path variable {orgId} , Path variable {depId} , Path variable {serviceName}
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationDepartmentsServiceNameDailyMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("serviceName") String serviceName);
        4.1 This getOrganizationDepartmentsServiceNameDailyMicroServices method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  service-cost-daily of an department an serviceName an Organization (List<object>) of the given organization id and department id and service-name
	5. JPA repository returns this list of  service-cost-daily of an department an serviceName  Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `12.3.organization and department wise service-cost-weekly`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service-cost/weekly
Request - Path variable {orgId} , Path variable {depId} , Path variable {serviceName}
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationDepartmentsServiceNameWeeklyMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("serviceName") String serviceName);
        4.1 This getOrganizationDepartmentsServiceNameWeeklyMicroServices method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  service-cost-daily-weekly of an department an serviceName an Organization (List<object>) of the given organization id and department id and service-name
	5. JPA repository returns this list of  service-cost-daily-weekly of an department an serviceName  Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `12.4.organization and department wise service-cost-monthly`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service-cost/monthly
Request - Path variable {orgId} , Path variable {depId} , Path variable {serviceName}
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationDepartmentsServiceNameMonthlyMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("serviceName") String serviceName);
        4.1 This getOrganizationDepartmentsServiceNameMonthlyMicroServices method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  service-cost-daily-monthly of an department an serviceName an Organization (List<object>) of the given organization id and department id and service-name
	5. JPA repository returns this list of  service-cost-daily-monthly of an department an serviceName  Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>


### `13. organization and department landingZone  and service wise`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/landing-zone/{landingZone}/services
Request - Path variable {orgId} , Path variable {depId} , Path variable {landingZone}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getOrganizationDepartmentsServiceNameMonthlyMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("landingZone") String landingZone);
        4.1 This getOrganizationDepartmentsServiceNameMonthlyMicroServices method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  service and services-name of an department an landingZone an Organization (List<String>) of the given organization id and department id and landingZone
	5. JPA repository returns this list of  service and services-name of an department an landingZone  Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `13.1.organization and department wise services landing-zone-products`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/landing-zone/{landingZone}/products
Request - Path variable {orgId} , Path variable {depId} , Path variable {landingZone}
Response - List<String>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<String> getOrganizationDepartmentsServiceNameMonthlyMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("landingZone") String landingZone);
        4.1 This getOrganizationDepartmentsServiceNameMonthlyMicroServices method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  service and product of an department an landingZone an Organization (List<String>) of the given organization id and department id and landingZone
	5. JPA repository returns this list of  service and product of an department an landingZone  Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `14. organization and department and service wise service-sla`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service-sla
Request - Path variable {orgId} , Path variable {depId} , Path variable {serviceName}
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationDepartmentServiceSlaMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("serviceName") String serviceName);
        4.1 This getOrganizationDepartmentServiceSlaMicroServices method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  service-cost of an department an serviceName an Organization (List<object>) of the given organization id and department id and service-name
	5. JPA repository returns this list of  service-cost of an department an serviceName  Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>



### `14.1.organization and department wise service-cureent-sla`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service/cureent-sla
Request - Path variable {orgId} , Path variable {depId} , Path variable {serviceName}
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationDepartmentServiceCureentSlaMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("serviceName") String serviceName);
        4.1 This getOrganizationDepartmentServiceCureentSlaMicroServices method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  service-cureent-sla of an department an serviceName an Organization (List<object>) of the given organization id and department id and service-name
	5. JPA repository returns this list of  service-cureent-sla of an department an serviceName  Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `14.2.organization and department wise service-weekly-sla`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service/weekly-sla 
Request - Path variable {orgId} , Path variable {depId} , Path variable {serviceName}
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationDepartmentServiceWeeklySlaMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("serviceName") String serviceName);
        4.1 This getOrganizationDepartmentServiceWeeklySlaMicroServices method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  service-weekly-sla of an department an serviceName an Organization (List<object>) of the given organization id and department id and service-name
	5. JPA repository returns this list of  service-weekly-sla of an department an serviceName  Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>

### `14.3.organization and department wise service-monthly-sla`
```
Method - GET
```
```
API End Point - /query/organizations/{orgId}/departments/{depId}/services/{serviceName}/service/monthly-sla
Request - Path variable {orgId} , Path variable {depId} , Path variable {serviceName}
Response - List<object>
```

	1. Request passed to spring boot request controller 
	2. Controller forward request to serivce class
	3. Service class calls JPA repository 
	4. There is method defines in the serive class - public List<object> getOrganizationDepartmentServiceMonthlySlaMicroServices(@Param("orgId") Long orgId, @Param("depId") Long depId,@Param("serviceName") String serviceName);
        4.1 This getOrganizationDepartmentServiceMonthlySlaMicroServices method accepts long type organization id and long type department id and pass it to the native sql
		4.2 Native sql returns the list of  service-monthly-sla of an department an serviceName an Organization (List<object>) of the given organization id and department id and service-name
	5. JPA repository returns this list of  service-monthly-sla of an department an serviceName  Organization to service class and service class returns the same list to contorller and finally controller wraps the list into the ResponseEntity and return it to client

<hr>



### Who do I talk to? ###

	Please mail us on
	info@syenctiks.com
Footer
© 2023 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About






