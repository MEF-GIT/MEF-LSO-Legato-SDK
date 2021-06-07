# CarrierEthernetVirtualUni
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**adminState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**identifier** | [**String**](string.md) | An identifier for the instance of the VUNI intended for operations purposes. | [optional] [default to null]
**sVlanId** | [**VlanId**](VlanId.md) |  | [optional] [default to null]
**defaultEnniCeVlanId** | [**VlanId**](VlanId.md) |  | [optional] [default to null]
**maximumNumberOfOvcEndPoints** | [**Integer**](integer.md) | The maximum number of OVC End Points that can be in the VUNI. | [optional] [default to null]
**maximumNumberOfEnniCeVlanIdsPerOvcEndPoint** | [**Integer**](integer.md) | The maximum number of ENNI CE-VLAN ID values that can be mapped to an OVC End Point that is in the VUNI. | [optional] [default to null]
**ingressBandwidthProfile** | [**List**](BwpFlow.md) | A Bandwidth Profile Flow for all ingress Frames mapped to the VUNI. Reference MEF 26.2 Section 15.1.6 VUNI Ingress Bandwidth Profile Service Attribute. | [optional] [default to null]
**egressBandwidthProfile** | [**List**](BwpFlow.md) | A Bandwidth Profile Flow for all egress Frames mapped to the VUNI.  Reference MEF 26.2 Section 15.1.7 VUNI Egress Bandwidth Profile Service Attribute. | [optional] [default to null]
**l2cpAddressSet** | [**L2cpAddressSet**](L2cpAddressSet.md) |  | [optional] [default to null]
**l2cpPeering** | [**L2cpPeering**](L2cpPeering.md) |  | [optional] [default to null]
**mepList** | [**List**](MepLevelAndDirection.md) | The indication of the instantiation of a MEP. A list with each item specifying the MEG Level. Reference MEF 26.2 Section 15.1.10 VUNI Maintenance End Point List Service Attribute. | [optional] [default to null]
**ovcEndPoint** | [**List**](CarrierEthernetOvcEndPointRef.md) | Reference to CarrierEthernetOvcEndPoint. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

