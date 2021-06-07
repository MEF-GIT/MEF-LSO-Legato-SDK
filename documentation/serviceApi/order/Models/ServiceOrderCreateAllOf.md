# ServiceOrderCreateAllOf
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
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

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

