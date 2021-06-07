# CosIdentifier
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**cosName** | [**String**](string.md) | This attribute denotes the Class of Service name that the CosIdentifier maps to. | [optional] [default to null]
**l2cpProtocolList** | [**List**](L2cpProtocol.md) | This attribute lists the L2CP protocols that map to the Class of Service name. | [optional] [default to null]
**sepCosIdPac** | [**List**](AnyType.md) | This attribute represents the relationship between the CosName and the SepCosId-Pac when the cosMappingType in Cos-Map is END_POINT and the cosName is not only for L2CP. | [optional] [default to null]
**pcpCosIdPac** | [**List**](PcpCosIdPac.md) | This attribute represents the relationship between the CosName and the PcpCosId-Pac when cosMappingType in CosMap is PCP and the cosName is not only for L2CP. | [optional] [default to null]
**dscpCosIdPac** | [**List**](DscpCosIdPac.md) | This attribute represents the relationship between the CosName and the Dscp-CosIdPac when the cosMappingType in CosMap is DSCP and the cosName is not only for L2CP. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

