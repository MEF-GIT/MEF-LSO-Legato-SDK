# CarrierEthernetEvcEndPoint
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**identifier** | [**String**](string.md) | A string that is used to allow the Subscriber and Service Provider to uniquely identify the EvcEndPoint for operations purposes. Reference MEF 10.4 Section 10.1 EVC EP ID Service Attribute. | [optional] [default to null]
**role** | [**EvcEndPointRole**](EvcEndPointRole.md) | Indicates how EI Frames mapped to the EVC End Point can be forwarded.  Reference MEF 10.4 Section 10.3 EVC EP Role Service Attribute. | [optional] [default to null]
**egressBandwidthProfilePerEndPoint** | [**List**](EgressBwpFlow.md) | Attribute used to limit the rate of all Egress Service Frames mapped to an EVC EP at a UNI. Reference MEF 10.4 Section 10.10 EVC EP Egress Bandwidth Profile Service Attribute. | [optional] [default to null]
**egressBandwidthProfilePerCosName** | [**List**](ClassOfServiceEgressBandwidthProfile.md) | Used to limit the rate of all Egress Service Frames with a given Class of Service Name, as determined at the ingress UNI for each frame per the EVC EP Ingress Class of Service Map Service Attribute. Reference MEF 10.4 Section 10.11 EVC EP Class of Service Name Egress Band-width Profile Service Attribute. | [optional] [default to null]
**egressMap** | [**List**](EvcEpEgressMap.md) |  | [optional] [default to null]
**evcEndPointMap** | [**VlanIdListOrUntag**](VlanIdListOrUntag.md) |  | [optional] [default to null]
**subscriberMegMip** | [**MegLevel**](MegLevel.md) |  | [optional] [default to null]
**carrierEthernetSubscriberUni** | [**CarrierEthernetSubscriberUniRef**](CarrierEthernetSubscriberUniRef.md) |  | [optional] [default to null]
**evc** | [**CarrierEthernetEvcRef**](CarrierEthernetEvcRef.md) |  | [optional] [default to null]
**administrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**ingressClassOfServiceMap** | [**CosMap**](CosMap.md) |  | [optional] [default to null]
**colorMap** | [**ColorIdentifier**](ColorIdentifier.md) |  | [optional] [default to null]
**ingressBandwidthProfilePerEndPoint** | [**List**](BwpFlow.md) | Bandwidth Profile Flow parameters for all ingress EI Frames mapped to the OVC End Point or EVC End Point. Reference MEF 26.2 Section 16.10 Ingress Band-width Profile per OVC End Point Service Attribute. Reference MEF 10.4 Section 10.8 EVC EP Ingress Bandwidth Profile Service Attribute. The absence of this attribute corresponds to a Service Attrib-ute of None. | [optional] [default to null]
**ingressBandwidthProfilePerCosName** | [**List**](BandwidthProfilePerClassOfServiceName.md) | For each CoS Name listed, Bandwidth Profile Flow parameters for all ingress EI Frames mapped to that CoS Name at the EVC End Point or OVC End Point. Reference MEF 26.2 Section 16.12 Ingress Bandwidth Profile per Class of Service Name Service and MEF 10.4 Section 10.9 EVC EP Class of Service Name Ingress Bandwidth Profile Service Attribute. | [optional] [default to null]
**sourceMacAddressLimit** | [**List**](SourceMacAddressLimit.md) | Specifies a limit on the number of differ-ent Source MAC address for which in-gress EI Frames at this EVC End Point or OVC End Point will be delivered. The absence of this attribute corresponds to a Service Attribute value of None. Refer-ence MEF 10.4 Section 10.12 EVC EP Source MAC Address Limit Service At-tribute and MEF 26.2 Section 16.15 OVC End Point Source MAC Address Limit Service Attribute. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

