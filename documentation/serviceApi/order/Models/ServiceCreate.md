# ServiceCreate
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Attype** | [**String**](string.md) | The concrete (non-abstract) class type of the API schema object. | [default to null]
**AtbaseType** | [**String**](string.md) | When sub-classing, this defines the super/base class type (if  applicable) of the API schema object. | [optional] [default to null]
**AtschemaLocation** | [**URI**](URI.md) | A URI refernce to the schema file that defines the attributes and relationships of the API schema object. | [optional] [default to null]
**category** | [**String**](string.md) | Is it a customer facing or resource facing service | [optional] [default to null]
**description** | [**String**](string.md) | Free-text description of the service | [optional] [default to null]
**mefServiceConfiguration** | [**MefServiceConfiguration**](MefServiceConfiguration.md) |  | [optional] [default to null]
**note** | [**List**](Note.md) |  | [optional] [default to null]
**place** | [**List**](Place.md) |  | [optional] [default to null]
**relatedParty** | [**List**](RelatedPartyRef.md) |  | [optional] [default to null]
**serviceCharacteristic** | [**List**](Characteristic.md) |  | [optional] [default to null]
**serviceRelationship** | [**List**](ServiceRelationship.md) |  | [optional] [default to null]
**serviceSpecification** | [**ServiceSpecificationRef**](ServiceSpecificationRef.md) |  | [optional] [default to null]
**serviceType** | [**String**](string.md) | Business type of the service  | [optional] [default to null]
**state** | [**ServiceStateType**](ServiceStateType.md) |  | [optional] [default to null]
**supportingResource** | [**List**](ResourceRef.md) |  | [optional] [default to null]
**supportingService** | [**List**](ServiceRef.md) | A list of supporting services (SupportingService [*]). A  collection of services that support this service (bundling,  link CFS to RFS). | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

