# ServiceCreateAllOf
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
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

