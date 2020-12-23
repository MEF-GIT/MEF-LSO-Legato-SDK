# CarrierEthernetOvcEndPoint
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**identifier** | [**String**](string.md) | An identifier for the OVC End Point intended for operating purposes. Reference MEF 26.2 Section 16.1 OVC End Point Identfier Service Attribute. | [optional] [default to null]
**role** | [**OvcEndPointRole**](OvcEndPointRole.md) |  | [optional] [default to null]
**endPointMap** | [**OvcEndPointMap**](OvcEndPointMap.md) |  | [optional] [default to null]
**egressMap** | [**List**](OvcEpEgressMap.md) |  | [optional] [default to null]
**egressEquivalenceClassIdentifier** | [**EecMap**](EecMap.md) |  | [optional] [default to null]
**egressBandwidthProfilePerEndPoint** | [**List**](BwpFlow.md) | Bandwidth Profile Flow parameters for all egress EI Frames mapped to the OVC End Point Reference MEF 26.2 Section 16.11 Egress Bandwidth Profile per OVC End Point Service Attribute. | [optional] [default to null]
**egressBandwidthProfilePerEec** | [**List**](BandwidthProfilePerEquivalenceClassName.md) | For each EEC Name listed, Bandwidth Profile Flow parameters, for all egress EI Frames mapped to that EEC Name at the OVC End Point. Reference MEF 26.2 Section 16.13 Egress Bandwidth Profile per Egress Equivalence Class Name Service Attribute. | [optional] [default to null]
**aggregationLinkDepth** | [**List**](AggLinkDepth.md) | The number of ENNI links that can carry ENNI Frames for each S-VLAN ID mapped to the OVC End Point.  Reference MEF 26.2 Section 16.14 OVC End Point Aggregation Link Depth Service Attribute. | [optional] [default to null]
**maintenanceIntermediatePoint** | [**String**](string.md) |  | [optional] [default to null]
**maintenanceEndPointList** | [**List**](MepLevelAndDirection.md) | The MEPs enable for the OVC End Point.  Reference MEF 26.2 Section 16.17 OVC End Point Maintenance End Point List Service Attribute. | [optional] [default to null]
**virtualUni** | [**List**](CarrierEthernetVirtualUniRef.md) |  | [optional] [default to null]
**operatorUni** | [**List**](CarrierEthernetOperatorUniRef.md) |  | [optional] [default to null]
**enniService** | [**List**](CarrierEthernetEnniServiceRef.md) |  | [optional] [default to null]
**ovc** | [**CarrierEthernetOvcRef**](CarrierEthernetOvcRef.md) |  | [optional] [default to null]
**administrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**ingressClassOfServiceMap** | [**CosMap**](CosMap.md) |  | [optional] [default to null]
**colorMap** | [**ColorIdentifier**](ColorIdentifier.md) |  | [optional] [default to null]
**ingressBandwidthProfilePerEndPoint** | [**List**](BwpFlow.md) | Bandwidth Profile Flow parameters for all ingress EI Frames mapped to the OVC End Point or EVC End Point. Reference MEF 26.2 Section 16.10 Ingress Band-width Profile per OVC End Point Service Attribute. Reference MEF 10.4 Section 10.8 EVC EP Ingress Bandwidth Profile Service Attribute. The absence of this attribute corresponds to a Service Attrib-ute of None. | [optional] [default to null]
**ingressBandwidthProfilePerCosName** | [**List**](BandwidthProfilePerClassOfServiceName.md) | For each CoS Name listed, Bandwidth Profile Flow parameters for all ingress EI Frames mapped to that CoS Name at the EVC End Point or OVC End Point. Reference MEF 26.2 Section 16.12 Ingress Bandwidth Profile per Class of Service Name Service and MEF 10.4 Section 10.9 EVC EP Class of Service Name Ingress Bandwidth Profile Service Attribute. | [optional] [default to null]
**sourceMacAddressLimit** | [**List**](SourceMacAddressLimit.md) | Specifies a limit on the number of differ-ent Source MAC address for which in-gress EI Frames at this EVC End Point or OVC End Point will be delivered. The absence of this attribute corresponds to a Service Attribute value of None. Refer-ence MEF 10.4 Section 10.12 EVC EP Source MAC Address Limit Service At-tribute and MEF 26.2 Section 16.15 OVC End Point Source MAC Address Limit Service Attribute. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

