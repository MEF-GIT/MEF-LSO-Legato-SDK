# OvcEpEgressMap
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**egressMapType** | [**OvcEgressMapType**](OvcEgressMapType.md) | This attribute determines which form to take to apply frame color indication, among CoS name and Ingress Color to C-Tag PCP, or CoS name and Ingress Color to S-Tag PCP, or CoS Name and Ingress Color to C-Tag DEI, or CoS Name to C-Tag PCP or CoS Name to S-Tag PCP. | [optional] [default to null]
**cosNameAndColorToDeiPacList** | [**List**](CosNameAndColorToDeiPac.md) | This attribute represents the relationship between the EgressMap and the CosNameAndColorToDeiPac (representing the attribute set for using CoS Name and ingress color to egress DEI mapping). | [optional] [default to null]
**cosNameToPcpPacList** | [**List**](CosNameToPcpPac.md) | This attribute represents the Egress Map that maps from CoS name to PCP. | [optional] [default to null]
**cosNameAndColorToPcpPacList** | [**List**](CosNameAndColorToPcpPac.md) | This attribute represents the relation between the EgressMap and the CosNameAndColorToPcpPac (representing the attribute using the CoS Name and ingress color to egress PCP mapping). | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

