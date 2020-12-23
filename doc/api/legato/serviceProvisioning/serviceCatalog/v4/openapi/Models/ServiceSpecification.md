# ServiceSpecification
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Attype** | [**String**](string.md) | The concrete (non-abstract) class type of the API schema object. | [default to null]
**AtbaseType** | [**String**](string.md) | When sub-classing, this defines the super/base class type (if  applicable) of the API schema object. | [optional] [default to null]
**AtschemaLocation** | [**URI**](URI.md) | A URI refernce to the schema file that defines the attributes and relationships of the API schema object. | [optional] [default to null]
**id** | [**String**](string.md) | Unique identifier of the API schema object instance. The  ID is invariant and is assigned by the server. In other words  this entity will have the same ID throught its lifetime. | [default to null]
**href** | [**URI**](URI.md) | URI reference of the API schema object instance. | [optional] [default to null]
**name** | [**String**](string.md) | Name of the API schema object instance. | [optional] [default to null]
**category** | [**String**](string.md) | The category is used to group service specifications in logical containers. Categories can be further sub-categorized into other categories. | [optional] [default to null]
**subcategory** | [**String**](string.md) | Categories can be further sub-categorized into other categories. | [optional] [default to null]
**version** | [**String**](string.md) | Service specification version | [optional] [default to null]
**descriptionDouble_Quote** | [**String**](string.md) | A narrative that explains  details of the service specification. | [optional] [default to null]
**isBundle** | [**Boolean**](boolean.md) | Determines whether a ServiceSpecification represents a single  ServiceSpecification (false), or a bundle of  ServiceSpecification (true). | [optional] [default to null]
**lastUpdate** | [**Date**](DateTime.md) | Date and time of the last update of the service specification | [optional] [default to null]
**validFor** | [**TimePeriod**](TimePeriod.md) | The period for which the service specification is valid | [optional] [default to null]
**lifecycleStatus** | [**ServiceSpecificationState**](ServiceSpecificationState.md) |  | [optional] [default to null]
**attachment** | [**List**](AttachmentRef.md) | A list of attachments (Attachment [*]). Complements  the description of the specification through video, pictures... | [optional] [default to null]
**relatedParty** | [**List**](RelatedPartyRef.md) |  | [optional] [default to null]
**serviceLevelSpecification** | [**List**](ServiceLevelSpecificationRef.md) | A list of service level specifications related to this service specification, and which will need to be satisifiable for corresponding service instances; e.g. Gold, Platinum | [optional] [default to null]
**serviceSpecRelationship** | [**List**](ServiceSpecificationRelationship.md) | A list of service specifications related to this specification, e.g. migration, substitution, dependency or exclusivity relationship | [optional] [default to null]
**serviceSpecCharacteristic** | [**List**](ServiceSpecCharacteristic.md) | A list of service spec characteristics (ServiceSpecCharacteristic [*]). This class represents the key features of this service specification. | [optional] [default to null]
**targetServiceSchema** | [**TargetServiceSchema**](TargetServiceSchema.md) |  | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

