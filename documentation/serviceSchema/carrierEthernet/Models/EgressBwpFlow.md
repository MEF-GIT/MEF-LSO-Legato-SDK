# EgressBwpFlow
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**cir** | [**Integer**](integer.md) | Attribute represents Committed Information Rate. When added to unused committed bandwidth provided from higher-ranked Bandwidth Profile Flows (depending on the value of CF for the higher-ranked Bandwidth Profile Flows), limits the average rate in bits per second at which Service Frames for this Bandwidth Profile Flow can be declared Green. | [optional] [default to null]
**cirMax** | [**Integer**](integer.md) | Attribute represents Maximum Committed Information Rate. Limits the average rate in bits per second at which Service Frames for this Bandwidth Profile Flow can be declared Green (regardless of unused committed bandwidth* from higher-ranked Bandwidth Profile Flows). | [optional] [default to null]
**rank** | [**Integer**](integer.md) | This attribute denotes the rank of the bandwidth profile flow in the envelope. | [optional] [default to null]
**envelope** | [**Envelope**](Envelope.md) | Identifies the Envelope that the Bandwidth Profile Flow belongs to, and the rank within the Envelope. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

