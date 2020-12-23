# CarrierEthernetOperatorUni
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**identifier** | [**String**](string.md) | An identifier for the UNI intended for management purposes. Reference MEF 26.2 Section 14.1 Operator UNI Identifier Service Attribute. | [optional] [default to null]
**synchronousMode** | [**List**](SyncModePerLink.md) |  | [optional] [default to null]
**numberOfLinks** | [**Integer**](integer.md) | The number of physical links at the UNI. Reference MEF 26.2 Section 14.4 Operator UNI Number of Links Service Attribute. | [optional] [default to null]
**physicalLayer** | [**List**](PhysicalLayer.md) | The physical layer of each of the links supporting the Operator UNI. Reference MEF 26.2 Section 14.2 Operator UNI Physical Layer Service Attribute. | [optional] [default to null]
**defaultCeVlanId** | [**VlanId**](VlanId.md) |  | [optional] [default to null]
**ingressBandwidthProfile** | [**List**](BwpFlow.md) |  | [optional] [default to null]
**egressBandwidthProfile** | [**List**](BwpFlow.md) |  | [optional] [default to null]
**elmi** | [**String**](string.md) |  | [optional] [default to null]
**ovcEndPoint** | [**List**](CarrierEthernetOvcEndPointRef.md) |  | [optional] [default to null]
**admininstrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**externalInterfaceframeFormat** | [**EthernetFrameFormat**](EthernetFrameFormat.md) |  | [optional] [default to null]
**linkOam** | [**EnabledDisabled**](EnabledDisabled.md) | Controls when and how Link OAM per IEEE Std 802.3-2015 is run on the physi-cal links in the External Interface. Refer-ence MEF 10.4 Section 9.13 Subscriber UNI Link OAM Service Attribute, MEF 26.2 Section 9.9 ENNI Link OAM Common Attribute and MEF 26.2 Section 14.14 Operator UNI Link OAM Service Attribute. | [optional] [default to null]
**l2cpPeering** | [**List**](L2cpPeering.md) | Specifies the Layer 2 Control Protocols that are peered at the EI, as described in MEF 45.1. Reference MEF 10.4 Section 9.17 Subscriber UNI L2CP Peering Service Attribute, MEF 26.2 Section 10.1 ENNI L2CP Peering Multilateral Attribute.  L2CP Peering applied to UNI and MEF 26.2 Section 14.21 Operator UNI L2CP Peering Service Attribute. | [optional] [default to null]
**lagLinkMeg** | [**EnabledDisabled**](EnabledDisabled.md) | Indicates whether a LAG link MEG is instantiated on each physical link in the EI, if the EI has more than one physical link. Reference MEF 10.4 Section 9.15 Subscriber UNI LAG Link MEG Service Attribute, MEF 26.2 Section 9.8 ENNI LAG Link MEG Common Attribute and MEF 26.2 Section 14.16 Operator UNI LAG Link MEG Service Attribute. | [optional] [default to null]
**meg** | [**EnabledDisabled**](EnabledDisabled.md) | Indicates whether a MEP is instantiated at the EI for the UNI MEG or ENNI MEG. Reference MEF 10.4 Section 9.14 Sub-scriber UNI MEG Service Attribute, MEF 26.2 Section 9.7 ENNI MEG Common Attribute and MEF 26.2 Section 14.15 Operator UNI MEG Service Attribute. | [optional] [default to null]
**aggregationLinkMap** | [**List**](ConversationIdToAggregationLinkMap.md) |  | [optional] [default to null]
**maximumFrameSize** | [**Integer**](integer.md) | Specifies the maximum size of EI Frames that can be transmitted across EI. Reference MEF 10.4 Section 9.8 Subscriber UNI Maximum Service Frame Size Service Attribute. Reference MEF 26.2 Section 14.8 Operator UNI Maximum Service Frame Size Service Attribute. Reference MEF 26.2 Section 10.3 ENNI Maximum Frame Size Multilateral Attribute. | [optional] [default to null]
**linkAggregation** | [**LinkAggregation**](LinkAggregation.md) |  | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

