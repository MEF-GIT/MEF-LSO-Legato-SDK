# SdWanVc
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**administrativeState** | [**AdministrativeState**](AdministrativeState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**swVcIdentifier** | [**String**](string.md) | Identification of the SWVC for management purposes. Reference MEF 70, Section 8.1. | [optional] [default to null]
**swVcEndPointList** | [**List**](SwVcEndPoint.md) | The SWVC End Point that are connected by the SWVC. Reference MEF 70 Section 8.2 SWVC End Point List Service Attribute. | [optional] [default to null]
**serviceUptimeObjective** | [**ServiceUptimeObjective**](ServiceUptimeObjective.md) |  | [optional] [default to null]
**ipv4ReservedPrefixes** | [**List**](Ipv4Prefix.md) | Specifies a list of IPv4 Prefixes that the Service Provider reserves for use for the SWVC within their own network or for distribution to the Subscriber via DHCP. Reference MEF 70 Section 8.4 SWVC Reserved Prefixes Service Attribute. | [optional] [default to null]
**ipv6ReservedPrefixes** | [**List**](Ipv6Prefix.md) | Specifies a list of IPv6 Prefixes that the Service Provider reserves for use for the SWVC within their own network or for distribution to the Subscriber via DHCP or SLAAC. Reference MEF 70 Section 8.4 SWVC Reserved Prefixes Service Attribute. | [optional] [default to null]
**listOfPolicies** | [**List**](Policy.md) | A list of the Policies that can be applied to Application Flows carried by the SWVC End Points. Reference MEF 10.4 Section 8.5 SWVC List of Policies Service Attribute. | [optional] [default to null]
**listOfApplicationFlows** | [**List**](ApplicationFlow.md) | Specifies the Application Flows that can be recognized by the SD-WAN service and information about how to identify IP packets in each Application Flow. Reference MEF 70 Section 8.7 SWVC List of Application Flows Service Attribute. | [optional] [default to null]
**listOfApplicationFlowGroups** | [**List**](ApplicationFlowGroup.md) | A list (possibly empty) of Application Flow Group names. Reference MEF 70 Section 8.6 SWVC List of Application Flow Groups Service Attribute. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

