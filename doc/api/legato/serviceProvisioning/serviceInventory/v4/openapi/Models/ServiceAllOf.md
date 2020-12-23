# ServiceAllOf
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**endDate** | [**Date**](DateTime.md) | Date when the service ends  | [optional] [default to null]
**hasStarted** | [**Boolean**](boolean.md) | If TRUE, this Service has already been started    | [optional] [default to null]
**isServiceEnabled** | [**Boolean**](boolean.md) | If FALSE, this particular Service has NOT been enabled for use  | [optional] [default to null]
**isStateful** | [**Boolean**](boolean.md) | If TRUE, this Service can be changed without affecting any other services | [optional] [default to null]
**serviceDate** | [**String**](string.md) | Date when the service was created (whatever its status). | [optional] [default to null]
**serviceOrder** | [**List**](ServiceOrderRef.md) |  | [optional] [default to null]
**startDate** | [**Date**](DateTime.md) | Date when the service starts | [optional] [default to null]
**startMode** | [**String**](string.md) | This attribute is an enumerated integer that indicates how the  Service is started, such as: 0: Unknown; 1: Automatically by  the managed environment; 2: Automatically by the owning device;  3: Manually by the Provider of the Service; 4: Manually by a  Customer of the Provider; 5: Any of the above  | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

