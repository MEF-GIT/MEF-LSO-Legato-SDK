# ServiceOrderItem
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Attype** | [**String**](string.md) | The concrete (non-abstract) class type of the API schema object. | [default to null]
**AtbaseType** | [**String**](string.md) | When sub-classing, this defines the super/base class type (if  applicable) of the API schema object. | [optional] [default to null]
**AtschemaLocation** | [**URI**](URI.md) | A URI refernce to the schema file that defines the attributes and relationships of the API schema object. | [optional] [default to null]
**id** | [**String**](string.md) | Identifier of the line item | [default to null]
**action** | [**ActionType**](ActionType.md) |  | [optional] [default to null]
**service** | [**ServiceCreate**](ServiceCreate.md) |  | [default to null]
**state** | [**ServiceOrderStateType**](ServiceOrderStateType.md) |  | [optional] [default to null]
**orderItemRelationship** | [**List**](ServiceOrderItemRelationship.md) |  | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

