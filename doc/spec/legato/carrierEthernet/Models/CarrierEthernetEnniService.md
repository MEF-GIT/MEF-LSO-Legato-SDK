# CarrierEthernetEnniService
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**operatorEnnIdentifier** | [**String**](string.md) | An identifier for the ENNI intended for management purposes. Reference MEF 26.2 Section 13.1 Operator ENNI Identifier Service Attribute. | [optional] [default to null]
**svlanIdControl** | [**SvlanIdControl**](SvlanIdControl.md) |  | [optional] [default to null]
**maximumNumberOfOvcs** | [**Integer**](integer.md) | The maximum number of OVCs that the Operator CEN can support at the ENNI. Reference MEF 26.2 Section 13.3 Maximum Number of OVCs Service Attribute. | [optional] [default to null]
**maximumNumberOfOvcEndPointsPerOvc** | [**Integer**](integer.md) | The maximum number of OVC End Points that the Operator CEN can support at the ENNI for an OVC. Reference MEF 26.2 Section 13.4 Maximum Number of OVC End Points per OVC Service Attribute. | [optional] [default to null]
**tokenShare** | [**String**](string.md) | An indication of the support of mapping more than one Bandwidth Profile Flow to an Envelope at the ENNI. Reference MEF 26.2 Section 13.5 ENNI Token Share Service Attribute. | [optional] [default to null]
**envelopes** | [**List**](Envelope.md) |  | [optional] [default to null]
**vuniList** | [**List**](CarrierEthernetVirtualUniRef.md) | Pointer to CarrierEthernetVirtualUnit(s). | [optional] [default to null]
**ovcEndPoint** | [**List**](CarrierEthernetOvcEndPointRef.md) | Pointer to CarrierEthernetOvcEnd-Point(s). | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

