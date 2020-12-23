# CarrierEthernetOvc
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**identifier** | [**String**](string.md) | An identifier for the OVC intended for managment purposes. Reference MEF 26.2 Section 12.1 OVC Identifier Service Attribute. | [optional] [default to null]
**ovcType** | [**ConnectionType**](ConnectionType.md) |  | [optional] [default to null]
**endPointList** | [**List**](CarrierEthernetOvcEndPoint.md) | A list of OVC End Points associated by the OVC. Reference MEF 26.2 Section 12.3 OVC End Point List Service Attribute. | [optional] [default to null]
**maximumNumberOfUniOvcEndPoints** | [**Integer**](integer.md) | The bound on the number of OVC End Points at different UNIs that can be associated by the OVC. Reference MEF 26.2 Section 12.4 Maximum Number of UNI OVC End Points Service Attribute. | [optional] [default to null]
**maximumNumberOfEnniOvcEndPoints** | [**Integer**](integer.md) | The bound on the number of OVC End Points at ENNIs that can be associated by the OVC. | [optional] [default to null]
**maximumFrameSize** | [**Integer**](integer.md) | This attributes denotes the maximum frame size in bytes. For EVC it is &gt;&#x3D;1522. For OVC it is &gt;&#x3D;1526. | [optional] [default to null]
**ovcCeVlanIdPreservation** | [**VlanIdPreservation**](VlanIdPreservation.md) |  | [optional] [default to null]
**ovcCeVlanPcpPreservation** | [**String**](string.md) |  | [optional] [default to null]
**ovcCeVlanDeiPreservation** | [**String**](string.md) |  | [optional] [default to null]
**ovcSvlanPcpPreservation** | [**String**](string.md) |  | [optional] [default to null]
**ovcSvlanDeiPreservation** | [**String**](string.md) |  | [optional] [default to null]
**listOfClassOfServiceNames** | [**List**](string.md) | A list of Class of Service Names. Reference MEF 26.2 Section 12.12 OVC List of Class of Service Names Service Attribute. | [optional] [default to null]
**frameDelivery** | [**FrameDisposition**](FrameDisposition.md) |  | [optional] [default to null]
**ovcL2cpAddressSet** | [**L2cpAddressSet**](L2cpAddressSet.md) |  | [optional] [default to null]
**administrativeState** | [**AdminState**](AdminState.md) |  | [optional] [default to null]
**operationalState** | [**OperationalState**](OperationalState.md) |  | [optional] [default to null]
**cTagPcpPreservation** | [**EnabledDisabled**](EnabledDisabled.md) | Whether the value of the PCP field in the C-Tag in Ingress EI Frames is preserved when the Egress EI Frame also has a C-Tag. Reference MEF 26.2 Section 12.8 OVC CE-VLAN PCP Preservation Service Attribute and MEF 10.4 Section 8.5 EVC C-Tag PCP Preservation Service Attribute. | [optional] [default to null]
**cTagDeiPreservation** | [**EnabledDisabled**](EnabledDisabled.md) | Whether the value of the DEI field in the C-Tag in Ingress Frames is preserved when the Egress EI Frame also has C-Tag. Reference MEF 26.2 Section 12.9 OVC CE-VLAN ID DEI Preservation Service Attribute and MEF 10.4 Section 8.6 EVC C-Tag DEI Preservation Service Attribute. | [optional] [default to null]
**connectionType** | [**ConnectionType**](ConnectionType.md) |  | [optional] [default to null]
**frameDisposition** | [**FrameDisposition**](FrameDisposition.md) |  | [optional] [default to null]
**listOfCosNames** | [**List**](string.md) | Used to specify all the Class of Service Names supported by an EVC or OVC. Reference MEF 10.4 Section 8.7 EVC List of Class of Service Names Service Attribute. The Class of Service Names supported by the OVC. Reference MEF 26.2 Section 12.12 OVC List of Class of Service Names Service Attribute. | [optional] [default to null]
**availableMegLevel** | [**List**](MegLevel.md) | The lowest MEG level for which SOAM Frames are not peered or discarded by the SP or Operator. If this attribute is not present there is no such level (that is, SOAM frames are all MEG levels may be peered or discarded by the SP or Opera-tor). Reference MEF 10.4 Section 8.11 EVC Available MEG Level Service Attribute and MEF 26.2 Section 12.15 OVC Available MEF Level Service Attribute. | [optional] [default to null]
**carrierEthernetSls** | [**List**](carrierEthernetSls.md) | Technical details of the service level in terms of Performance Objectives, agreed between the Service Provider and the Subscriber or between Service Provider and the Operator as part of the Service Level Agreement. A given SLS might contain 0,1 or more Performance Objec-tives for each Performance Metric.  Ref-erence MEF 10.4 Section 8.8 EVC Ser-vice Level Specification Service Attribute and MEF 26.2 Section 12.13 OVC Service Level Specification Service Attribute. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

