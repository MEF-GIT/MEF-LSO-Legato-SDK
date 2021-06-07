# AttachmentRef
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Attype** | [**String**](string.md) | The concrete (non-abstract) class type of the API schema object. | [default to null]
**AtbaseType** | [**String**](string.md) | When sub-classing, this defines the super/base class type (if  applicable) of the API schema object. | [optional] [default to null]
**AtschemaLocation** | [**URI**](URI.md) | A URI refernce to the schema file that defines the attributes and relationships of the API schema object. | [optional] [default to null]
**id** | [**String**](string.md) | Unique identifier of the API schema object instance. The  ID is invariant and is assigned by the server. In other words  this entity will have the same ID throught its lifetime. | [default to null]
**href** | [**URI**](URI.md) | URI reference of the API schema object instance. | [optional] [default to null]
**name** | [**String**](string.md) | Name of the API schema object instance. | [optional] [default to null]
**AtreferredType** | [**String**](string.md) | The class type of the target API schema object instance. | [default to null]
**description** | [**String**](string.md) | A narrative text describing the content of the attachment | [optional] [default to null]
**url** | [**URI**](URI.md) | Link to the attachment media/content | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

