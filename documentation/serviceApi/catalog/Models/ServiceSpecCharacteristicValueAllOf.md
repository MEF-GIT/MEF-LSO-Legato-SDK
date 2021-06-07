# ServiceSpecCharacteristicValueAllOf
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**isDefault** | [**Boolean**](boolean.md) | Indicates if the value is the default value for a characteristic | [optional] [default to null]
**rangeInterval** | [**String**](string.md) | An indicator that specifies the inclusion or exclusion of the valueFrom and valueTo attributes. If applicable, possible  values are \&quot;open\&quot;, \&quot;closed\&quot;, \&quot;closedBottom\&quot; and \&quot;closedTop\&quot;. | [optional] [default to null]
**regex** | [**String**](string.md) | A regular expression constraint for given value | [optional] [default to null]
**unitOfMeasure** | [**String**](string.md) | A length, surface, volume, dry measure, liquid measure, money,  weight, time, and the like. In general, a determinate quantity  or magnitude of the kind designated, taken as a standard of  comparison for others of the same kind, in assigning to them  numerical values, as 1 foot, 1 yard, 1 mile, 1 square foot. | [optional] [default to null]
**valueFrom** | [**Integer**](integer.md) | The low range value that a characteristic can take on | [optional] [default to null]
**valueTo** | [**Integer**](integer.md) | The upper range value that a characteristic can take on | [optional] [default to null]
**valueType** | [**String**](string.md) | A kind of value that the characteristic can take on, such as numeric,  text, and so forth | [optional] [default to null]
**validFor** | [**TimePeriod**](TimePeriod.md) | The period of time for which a value is applicable | [optional] [default to null]
**value** | [**Map**](object.md) | A discrete value that the characteristic can take on, or the actual value of the characteristic | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

