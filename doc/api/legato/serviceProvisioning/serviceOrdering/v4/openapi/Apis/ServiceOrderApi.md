# ServiceOrderApi

All URIs are relative to *https://mef.net:8443/mefApi/legato/serviceOrdering/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**serviceOrderCreate**](ServiceOrderApi.md#serviceOrderCreate) | **POST** /serviceOrder | Create a service order
[**serviceOrderFind**](ServiceOrderApi.md#serviceOrderFind) | **GET** /serviceOrder | List service orders
[**serviceOrderGet**](ServiceOrderApi.md#serviceOrderGet) | **GET** /serviceOrder/{id} | Retrieve a service order


<a name="serviceOrderCreate"></a>
# **serviceOrderCreate**
> ServiceOrder serviceOrderCreate(serviceOrderCreate)

Create a service order

    This operation creates a Service Order instance in the Service Order management system maintained by the SOF. A Service Order is used to request operations on a Service instance. A Service Order groups one or more one Service Order Items - one per specific action on a Service instance. The Action associated with the Service Order Item describes the operation (add, remove, update) to be applied on the specified Service instance. The Service Order Item and its associated Action can operate on both existing (remove, update) as well as future (add) Service instance. The Service Order is triggered from the Business Application (BA) system in charge of the Product Order management to the Service Orchestration Function (SOF) system that will orchestrate the Service fulfillment. The assumption is that the Service Specifications describing the Service instance in the Service Order Item are already available (to both BA &amp; SOF). If an exception is encountered, then appropriate returnCode and error information is populated and returned as specified.

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **serviceOrderCreate** | [**ServiceOrderCreate**](../\Models/ServiceOrderCreate.md)|  |

### Return type

[**ServiceOrder**](../\Models/ServiceOrder.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json;charset=utf-8
- **Accept**: application/json;charset=utf-8

<a name="serviceOrderFind"></a>
# **serviceOrderFind**
> List serviceOrderFind(externalId, state, category, orderDatePeriodgt, orderDatePeriodlt, fields, offset, limit)

List service orders

    This operation returns a list of Service Order instances matching the query parameters from the Service Order management system maintained by the SOF. Attribute selection is possible using the &#39;&#39;fields&#39;&#39; parameter to filter retrieved attribute(s) for each Service Order instance. If an exception is encountered, then appropriate returnCode and error information is populated and returned as specified.

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **externalId** | **String**|  Filter by externalId | [optional] [default to null]
 **state** | [**ServiceOrderStateType**](../\Models/.md)|  State of the order(s) to be retrieved | [optional] [default to null] [enum: ACKNOWLEDGED, IN_PROGRESS, PENDING, HELD, CANCELLED, COMPLETED, FAILED, PARTIAL, REJECTED]
 **category** | **String**| Category of the service order to be retrieved  | [optional] [default to null]
 **orderDatePeriodgt** | **Date**| Service Order date (creation) greather than | [optional] [default to null]
 **orderDatePeriodlt** | **Date**| Service Order date (creation) lower than | [optional] [default to null]
 **fields** | **String**| Comma-separated properties of the Service Order to be included in  the returned response | [optional] [default to null]
 **offset** | **Integer**| Requested start index in a ordered list (sorted by id property) of  matching Service Orders to be provided in response.  | [optional] [default to null]
 **limit** | **Integer**| Requested maximum number of Service Orders to be provided  in the response | [optional] [default to null]

### Return type

[**List**](../\Models/ServiceOrder.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json;charset=utf-8

<a name="serviceOrderGet"></a>
# **serviceOrderGet**
> ServiceOrder serviceOrderGet(id, fields)

Retrieve a service order

    This operation retrieves a Service Order instance identified by the Id parameter from the Service Order managment system maintained by the SOF. Attribute selection is possible using the &#39;&#39;fields&#39;&#39; parameter to filter retrieved attribute(s) for the returned Service Order instance. If an exception is encountered, then appropriate returnCode and error information is populated and returned as specified.

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **String**| Identifier of the ServiceOrder | [default to null]
 **fields** | **String**| Comma-separated properties of the Service Order to be included in  the returned response | [optional] [default to null]

### Return type

[**ServiceOrder**](../\Models/ServiceOrder.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json;charset=utf-8

