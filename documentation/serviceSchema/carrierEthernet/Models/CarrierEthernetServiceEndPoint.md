# CarrierEthernetServiceEndPoint
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**administrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**ingressClassOfServiceMap** | [**CosMap**](CosMap.md) |  | [optional] [default to null]
**colorMap** | [**ColorIdentifier**](ColorIdentifier.md) |  | [optional] [default to null]
**ingressBandwidthProfilePerEndPoint** | [**List**](BwpFlow.md) | Bandwidth Profile Flow parameters for all ingress EI Frames mapped to the OVC End Point or EVC End Point. Reference MEF 26.2 Section 16.10 Ingress Band-width Profile per OVC End Point Service Attribute. Reference MEF 10.4 Section 10.8 EVC EP Ingress Bandwidth Profile Service Attribute. The absence of this attribute corresponds to a Service Attrib-ute of None. | [optional] [default to null]
**ingressBandwidthProfilePerCosName** | [**List**](BandwidthProfilePerClassOfServiceName.md) | For each CoS Name listed, Bandwidth Profile Flow parameters for all ingress EI Frames mapped to that CoS Name at the EVC End Point or OVC End Point. Reference MEF 26.2 Section 16.12 Ingress Bandwidth Profile per Class of Service Name Service and MEF 10.4 Section 10.9 EVC EP Class of Service Name Ingress Bandwidth Profile Service Attribute. | [optional] [default to null]
**sourceMacAddressLimit** | [**List**](SourceMacAddressLimit.md) | Specifies a limit on the number of differ-ent Source MAC address for which in-gress EI Frames at this EVC End Point or OVC End Point will be delivered. The absence of this attribute corresponds to a Service Attribute value of None. Refer-ence MEF 10.4 Section 10.12 EVC EP Source MAC Address Limit Service At-tribute and MEF 26.2 Section 16.15 OVC End Point Source MAC Address Limit Service Attribute. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

