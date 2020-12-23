# SlsCosNameEntry
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**cosName** | [**String**](string.md) | Class of Service name. | [optional] [default to null]
**deltaT** | [**Integer**](integer.md) | This attribute denotes the delta-T, a time interval in seconds, smaller than T (SLS time period). | [optional] [default to null]
**thresholdC** | [**BigDecimal**](number.md) | Denotes the threshold for FLR, used to determine whether a given time interval delta t has high loss. | [optional] [default to null]
**consecutiveIntervalN** | [**Integer**](integer.md) | This attribute denotes n, used to identify how many consecutive delta-T intervals must have high loss to trigger a change in Availability. | [optional] [default to null]
**oneWayFrameDelayPmMetric** | [**List**](OneWayFrameDelayPmMetric.md) | Pointer to One-way Frame Delay Performance Management Metric. | [optional] [default to null]
**oneWayInterFrameDelayVariationPmMetric** | [**List**](OneWayInterFrameDelayVariationPmMetric.md) | Pointer to One-way Inter-Frame Delay Variation Performance Management Metric. | [optional] [default to null]
**oneWayMeanFrameDelayPmMetric** | [**List**](OneWayMeanFrameDelayPmMetric.md) | Pointer to One-way Mean Frame Delay Performance Management Metric. | [optional] [default to null]
**oneWayFrameLossRatioPmMetric** | [**List**](OneWayFrameLossRatioPmMetric.md) | Pointer to One-way Frame Loss Ratio Performance Management Metric. | [optional] [default to null]
**oneWayMeanFrameDelayRangePmMetric** | [**List**](OneWayMeanFrameDelayRangePmMetric.md) | Pointer to One-way Frame Delay Range Performance Management Metric. | [optional] [default to null]
**oneWayAvailabilityPmMetric** | [**List**](OneWayAvailabilityPmMetric.md) | Pointer to One-way Availability Performance Management Metric. | [optional] [default to null]
**oneWayHighLossIntervalPmMetric** | [**List**](OneWayHighLossIntervalPmMetric.md) | Pointer to One-way High Loss Interval Performance Management Metric. | [optional] [default to null]
**oneWayConsecutiveHighLossIntervalsPmMetric** | [**List**](OneWayConsecutiveHighLossIntervalsPmMetric.md) | Pointer to One-way Consecutive High Loss Interval Performance Management Metric. | [optional] [default to null]
**oneWayCompositePmMetric** | [**List**](OneWayCompositePmMetric.md) | Pointer to One-way Composite Performance Management Metric. | [optional] [default to null]
**oneWayGroupAvailabilityPmMetric** | [**List**](OneWayGroupAvailabilityPmMetric.md) | Pointer to One-way Group Availability Performance Management Metric. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

