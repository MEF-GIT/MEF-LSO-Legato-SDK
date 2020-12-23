# ServiceSpecCharacteristic
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Attype** | [**String**](string.md) | The concrete (non-abstract) class type of the API schema object. | [default to null]
**AtbaseType** | [**String**](string.md) | When sub-classing, this defines the super/base class type (if  applicable) of the API schema object. | [optional] [default to null]
**AtschemaLocation** | [**URI**](URI.md) | A URI refernce to the schema file that defines the attributes and relationships of the API schema object. | [optional] [default to null]
**id** | [**String**](string.md) | Unique identifier of the API schema object instance. The  ID is invariant and is assigned by the server. In other words  this entity will have the same ID throught its lifetime. | [default to null]
**href** | [**URI**](URI.md) | URI reference of the API schema object instance. | [optional] [default to null]
**name** | [**String**](string.md) | Name of the API schema object instance. | [optional] [default to null]
**AtvalueSchemaLocation** | [**String**](string.md) | This (optional) field provides a link to the schema describing  the value type. | [optional] [default to null]
**valueType** | [**String**](string.md) | A kind of value that the characteristic can take on, such as numeric, text and so forth | [optional] [default to null]
**description** | [**String**](string.md) | A narrative that explains in details the nature of the serviceSpecCharacteristic | [optional] [default to null]
**extensible** | [**Boolean**](boolean.md) | An indicator that specifies that the values for the  characteristic can be extended by adding new values when  instantiating a characteristic for an Entity. | [optional] [default to null]
**isUnique** | [**Boolean**](boolean.md) | An indicator that specifies if a value is unique for the specification. Possible values are; \&quot;unique while value is in effect\&quot; and \&quot;unique whether value is in effect or not\&quot; | [optional] [default to null]
**maxCardinality** | [**Integer**](integer.md) | The maximum number of instances a CharacteristicValue can take on. For example, zero to five phone numbers in a group calling plan, where five is the value for the maxCardinality. | [optional] [default to null]
**minCardinality** | [**Integer**](integer.md) | The minimum number of instances a CharacteristicValue can take on. For example, zero to five phone numbers in a group calling plan, where  zero is the value for the minCardinality. | [optional] [default to null]
**regex** | [**String**](string.md) | A rule or principle represented in regular expression used to derive the value of a characteristic value. | [optional] [default to null]
**validFor** | [**TimePeriod**](TimePeriod.md) | The period for which the serviceSpecCharacteristic is valid | [optional] [default to null]
**serviceSpecCharRelationship** | [**List**](ServiceSpecificationRelationship.md) | A list of service spec char relationships. An aggregation, migration, substitution, dependency or exclusivity relationship between/among Specification Characteristics. | [optional] [default to null]
**serviceSpecCharacteristicValue** | [**List**](ServiceSpecCharacteristicValue.md) | A list of service spec characteristic values. A  ServiceSpecCharacteristicValue object is used to define a set  of attributes, each of which can be assigned to a corresponding  set of attributes in a ServiceSpecCharacteristic object. The  values of the attributes in the ServiceSpecCharacteristicValue  object describe the values of the attributes that a  corresponding ServiceSpecCharacteristic object can take on. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

