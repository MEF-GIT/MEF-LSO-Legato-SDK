# Error
## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**code** | [**Integer**](integer.md) | Application related code. List of supported error codes are defined below:  **400: Bad Request** - 20: Invalid URL parameter value - 21: Missing body - 22: Invalid body - 23: Missing body field - 24: Invalid body field - 25: Missing header - 26: Invalid header value - 27: Missing query-string parameter - 28: Invalid query-string parameter value  **401: Unauthorized** - 40: Missing credentials - 41: Invalid credentials - 42: Expired credentials  **403: Forbidden** - 50: Access denied - 51: Forbidden requester - 52: Forbidden user - 53: Too many requests  **404: Not Found** - 60: Resource not found  **405: Method Not Allowed** - 61: Method not allowed  **408: Request Timeout** - 63: Request time-out  **409: Conflict** - 64: Resource Conflict  **422: Unprocessable Entity** - Functional Error codes specific to operation  **500: Internal Server Error** - 1: Internal Error  **501: Not Implemented**  **503: Service Unavailable** | [default to null]
**reason** | [**String**](string.md) | Text that explains the reason for error. This can be shown to a client user. | [default to null]
**message** | [**List**](string.md) | Text that provides more details and corrective actions related to the error. This can be shown to a client user. | [optional] [default to null]
**status** | [**List**](string.md) | HTTP error code extension like 400-2. | [optional] [default to null]
**referenceError** | [**List**](string.md) | URI pointing to (external) documentation describing the error. | [optional] [default to null]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

