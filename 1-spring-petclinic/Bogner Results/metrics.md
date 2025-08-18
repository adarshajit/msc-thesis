# Number of Services Involved in the Compound Service (NSIC)

## Description
Number of services involved in the compound service

## Interpretation
Value range: [0,4], lower is better

## Results

- visits-service: 1
- api-gateway: 1
- customers-service: 1
- vets-service: 1


# Services Interdependence in the System (SIY)

## Description
Count of pairs of services which depend on each other

## Interpretation
Value range: [0,6], lower is better

## Result
0


# Absolute Importance of the Service (AIS)

## Description
Number of services which depend on a service

## Interpretation
Value range: [0,3], lower is better

## Results

- visits-service: 1
- api-gateway: 1
- customers-service: 0
- vets-service: 1


# Absolute Dependence of the Service (ADS)

## Description
Number of other services a service depends on

## Interpretation
Value range: [0,3], lower is better

## Results

- visits-service: 0
- api-gateway: 0
- customers-service: 0
- vets-service: 0


# Absolute Criticality of the Service (ACS)

## Description
Product of its absolute importance (AIS) and absolute dependence (ADS)

## Interpretation
Value range: [0,9], lower is better

## Results

- visits-service: 0
- api-gateway: 0
- customers-service: 0
- vets-service: 0


# Number of Services (NS)

## Description
Number of services in the system

## Interpretation
Value range: [0,INF), lower is better

## Result
4


# Relative Coupling of Service (RCS)

## Description
Degree to which a service depends on the other services

## Interpretation
Value range: [0,100), lower is better

## Results (Dynamic)

- visits-service: 33.3%
- api-gateway: 100%
- customers-service: 33.3%
- vets-service: 33.3%


# Relative Importance of Service (RIS)

## Description
Degree to which the other services depend on a service

## Interpretation
Value range: [0,100), lower is better

## Results (Dynamic)

- visits-service: 33.3%
- api-gateway: 0%
- customers-service: 33.3%
- vets-service: 33.3%


# Service Coupling Factor (SCF)

## Description
Indicates the overall coupling in the system, the sum over all single coupling values is set in relation with the maximum couplings that could occur in the system

## Interpretation
Value range: [0,1], lower is better

## Result
0.2


# Weighted Service Interface Count (WSIC)

## Description
Weighted number of exposed interfaces or operations per service (all weights = 1.0)

## Interpretation
Value range: [0,INF), lower is better

## Results

- visits-service: 7.0
- api-gateway: 11.0
- customers-service: 11.0
- vets-service: 5.0


# Service Composition Pattern (SCP)

## Description
Fraction of services which are composite

## Interpretation
Value range: [0,100], lower is better

## Result
0%


# Inverse of Average Number of Used Message (IAUM)

## Description
Ratio between number of services and message types

## Interpretation
Value range: (0,1], very low values should be avoided

## Result
0.12


# Service Interface Usage Cohesion (SIUC)

## Description
Quantifies cohesion of a service based on the number of operations invoked by every client

## Interpretation
Value range: (0,100], higher is better

## Results

- visits-service: 33%
- api-gateway: 0%
- customers-service: 100%
- vets-service: 0%

# Service Interface Data Cohesion (SIDC)

## Description
Quantifies cohesion of a service based on the number of operations sharing the same input parameter types

## Interpretation
Value range: [0,100], higher is better

## Results

- visits-service: 0%
- api-gateway: 0%
- customers-service: 0%
- vets-service: 0%


# Response for Operation (RFO)

## Description
Cardinality of the set of other service interfaces that can be executed in response to invocations with all possible parameters

## Interpretation
Value range: [0,INF), lower is better

## Results

- visits-service:
    - \[http get /actuator/info\]: 0
    - \[http get /actuator\]: 0
    - \[http get /actuator/health\]: 1
    - \[http get /pets/visits\]: 1
    - \[http post /owners/\*/pets/{petid}/visits\]: 1
    - \[http get /owners/\*/pets/{petid}/visits\]: 1
    - \[http get /actuator/prometheus\]: 0

- api-gateway:
    - \[http get\]: 1
    - \[http put\]: 1
    - \[http get /actuator/info\]: 0
    - \[http get /actuator\]: 0
    - \[http get /actuator/health\]: 0
    - \[http get /webjars/\*\*\]: 0
    - \[http post /fallback\]: 0
    - \[http get /api/gateway/owners/{ownerid}\]: 0
    - \[http get /actuator/prometheus\]: 0
    - \[http post\]: 1
    - \[http get /\]: 0

- customers-service:
    - \[http post /owners\]: 1
    - \[http post /owners/{ownerid}/pets\]: 1
    - \[http get /pettypes\]: 1
    - \[http get /actuator/info\]: 0
    - \[http get /actuator\]: 0
    - \[http get /actuator/health\]: 1
    - \[http get /owners/{ownerid}\]: 1
    - \[http get /owners\]: 1
    - \[http put /owners/\*/pets/{petid}\]: 1
    - \[http get /actuator/prometheus\]: 0
    - \[http get /owners/\*/pets/{petid}\]: 1

- vets-service:
    - \[http get /actuator/info\]: 0
    - \[http get /actuator\]: 0
    - \[http get /actuator/health\]: 1
    - \[http get /actuator/prometheus\]: 0
    - \[http get /vets\]: 1

## Details

- api-gateway (\[http get\]): \[http get\]
- api-gateway (\[http post\]): \[http post\]
- api-gateway (\[http put\]): \[http put\]
- customers-service (\[http get /owners\]): \[connection\]
- customers-service (\[http post /owners/{ownerid}/pets\]): \[connection\]
- customers-service (\[http get /owners/{ownerid}\]): \[connection\]
- customers-service (\[http get /pettypes\]): \[connection\]
- customers-service (\[http put /owners/\*/pets/{petid}\]): \[connection\]
- customers-service (\[http get /owners/\*/pets/{petid}\]): \[connection\]
- customers-service (\[http post /owners\]): \[connection\]
- customers-service (\[http get /actuator/health\]): \[connection\]
- vets-service (\[http get /vets\]): \[connection\]
- vets-service (\[http get /actuator/health\]): \[connection\]
- visits-service (\[http post /owners/\*/pets/{petid}/visits\]): \[connection\]
- visits-service (\[http get /owners/\*/pets/{petid}/visits\]): \[connection\]
- visits-service (\[http get /actuator/health\]): \[connection\]
- visits-service (\[http get /pets/visits\]): \[connection\]


# Total Response for Service (TRS)

## Description
Sum of RFO values for all operations

## Interpretation
Value range: [0,INF), lower is better

## Result
17


# Mean Absolute Importance/Dependence in the System (MAIDS)

## Description
Mean number of services which depend on a service / Mean number of services a service depends on

## Interpretation
Value range: [0,3], lower is better

## Result
0.75


# Mean Absolute Coupling in the System (MACS)

## Description
Mean number of services which depend on a service or a service depends on

## Interpretation
Value range: [0,6], lower is better

## Result
1.5


# Dynamic Relative Dependence of Service (DRDS)

## Description
Degree to which a service uses other services in terms of calls

## Interpretation
Value range: (0,100], higher is better

## Results


# Dynamic Relative Importance of Service (DRIS)

## Description
Degree to which other services depend on a service in terms of calls

## Interpretation
Value range: (0,100], higher is better

## Results


# Dynamic Relative Dependence of Service in the System (DRDSS)

## Description
Degree to which a service uses other services in terms of calls compared to all calls system-wide

## Interpretation
Value range: (0,100], lower is better

## Results


# Dynamic Relative Importance of Service in the System (DRISS)

## Description
Degree to which other services depend on a service in terms of calls compared to all calls system-wide

## Interpretation
Value range: (0,100], lower is better

## Results


# Cyclic Service Dependencies (CSD)

## Description
Number of cycles in the dependencies

## Interpretation
Value range: [0,14], lower is better

## Result
0

## Details
