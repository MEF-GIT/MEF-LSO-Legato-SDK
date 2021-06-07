# ServiceOrder
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Attype** | [**String**](string.md) | The concrete (non-abstract) class type of the API schema object. | [default to null]
**AtbaseType** | [**String**](string.md) | When sub-classing, this defines the super/base class type (if  applicable) of the API schema object. | [optional] [default to null]
**AtschemaLocation** | [**URI**](URI.md) | A URI refernce to the schema file that defines the attributes and relationships of the API schema object. | [optional] [default to null]
**id** | [**String**](string.md) | Unique identifier of the API schema object instance. The  ID is invariant and is assigned by the server. In other words  this entity will have the same ID throught its lifetime. | [default to null]
**href** | [**URI**](URI.md) | URI reference of the API schema object instance. | [optional] [default to null]
**name** | [**String**](string.md) | Name of the API schema object instance. | [optional] [default to null]
**externalId** | [**String**](string.md) | ID given by the consumer and only understandable by client (to facilitate client searches) | [optional] [default to null]
**description** | [**String**](string.md) | A free-text description of the service order | [optional] [default to null]
**category** | [**String**](string.md) | Used to categorize the order that can be useful for OM system (e.g. “broadband”, “TVOption”, ...)&#39; | [optional] [default to null]
**note** | [**List**](Note.md) |  | [optional] [default to null]
**notificationContact** | [**String**](string.md) | Contact attached to the order to send back information  regarding this order | [optional] [default to null]
**priority** | [**Integer**](integer.md) | A way that can be used by consumers to prioritize orders in Service Order Management system (from 0 to 4 : 0 is the highest priority, and 4 the lowest | [optional] [default to null]
**requestedStartDate** | [**Date**](DateTime.md) | Order start date wished by the requestor | [optional] [default to null]
**requestedCompletionDate** | [**Date**](DateTime.md) | Requested delivery date from the requestor perspective | [optional] [default to null]
**relatedParty** | [**List**](RelatedPartyRef.md) |  | [optional] [default to null]
**orderItem** | [**List**](ServiceOrderItem.md) |  | [optional] [default to null]
**orderRelationship** | [**List**](ServiceOrderRelationship.md) |  | [optional] [default to null]
**state** | [**ServiceOrderStateType**](ServiceOrderStateType.md) |  | [optional] [default to null]
**orderDate** | [**Date**](DateTime.md) | Date when the order was created. | [optional] [default to null]
**startDate** | [**Date**](DateTime.md) | Date when the order processing was started | [optional] [default to null]
**expectedCompletionDate** | [**Date**](DateTime.md) | Expected delivery date set by the provider. | [optional] [default to null]
**completionDate** | [**Date**](DateTime.md) | Date when the order was completed | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

