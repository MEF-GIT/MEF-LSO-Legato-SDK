# EecIdentifier
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**eecName** | [**String**](string.md) | This attribute denotes the Egress Equiva-lence Class Name that the EecIdentifier maps to. | [optional] [default to null]
**l2cpProtocolList** | [**List**](L2cpProtocol.md) | This attribute lists the L2CP protocols that map to the Egress Equivalence Class Name. | [optional] [default to null]
**pcpEecIdPac** | [**List**](PcpEecIdPac.md) | This attribute represents the relationship between the EecIdentifier and a PcpEecIdPac if the eecMappingType in EecMap is PCP and the eecName is not only for L2CP. | [optional] [default to null]
**dscpEecIdPac** | [**List**](DscpEecIdPac.md) | This attribute represents the relationship between the EecIdentifier and a DscpEecIdPac if the eecMappingType in EecMap is DSCP and the eecName is not only for L2CP. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

