# CarrierEthernetService
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**administrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**cTagPcpPreservation** | [**EnabledDisabled**](EnabledDisabled.md) | Whether the value of the PCP field in the C-Tag in Ingress EI Frames is preserved when the Egress EI Frame also has a C-Tag. Reference MEF 26.2 Section 12.8 OVC CE-VLAN PCP Preservation Service Attribute and MEF 10.4 Section 8.5 EVC C-Tag PCP Preservation Service Attribute. | [optional] [default to null]
**cTagDeiPreservation** | [**EnabledDisabled**](EnabledDisabled.md) | Whether the value of the DEI field in the C-Tag in Ingress Frames is preserved when the Egress EI Frame also has C-Tag. Reference MEF 26.2 Section 12.9 OVC CE-VLAN ID DEI Preservation Service Attribute and MEF 10.4 Section 8.6 EVC C-Tag DEI Preservation Service Attribute. | [optional] [default to null]
**connectionType** | [**ConnectionType**](ConnectionType.md) |  | [optional] [default to null]
**frameDisposition** | [**FrameDisposition**](FrameDisposition.md) |  | [optional] [default to null]
**listOfCosNames** | [**List**](string.md) | Used to specify all the Class of Service Names supported by an EVC or OVC. Reference MEF 10.4 Section 8.7 EVC List of Class of Service Names Service Attribute. The Class of Service Names supported by the OVC. Reference MEF 26.2 Section 12.12 OVC List of Class of Service Names Service Attribute. | [optional] [default to null]
**maximumFrameSize** | [**Integer**](integer.md) | Maximum size of EI frames that can be carried over the EVC or OVC. Reference MEF 10.4 Section 8.10 EVC Maximum Service Frame Size Service Attribute and MEF 26.2 Section 12.6 OVC Maximum Frame Size Service Attribute. | [optional] [default to null]
**availableMegLevel** | [**List**](MegLevel.md) | The lowest MEG level for which SOAM Frames are not peered or discarded by the SP or Operator. If this attribute is not present there is no such level (that is, SOAM frames are all MEG levels may be peered or discarded by the SP or Opera-tor). Reference MEF 10.4 Section 8.11 EVC Available MEG Level Service Attribute and MEF 26.2 Section 12.15 OVC Available MEF Level Service Attribute. | [optional] [default to null]
**carrierEthernetSls** | [**List**](carrierEthernetSls.md) | Technical details of the service level in terms of Performance Objectives, agreed between the Service Provider and the Subscriber or between Service Provider and the Operator as part of the Service Level Agreement. A given SLS might contain 0,1 or more Performance Objec-tives for each Performance Metric.  Ref-erence MEF 10.4 Section 8.8 EVC Ser-vice Level Specification Service Attribute and MEF 26.2 Section 12.13 OVC Service Level Specification Service Attribute. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

