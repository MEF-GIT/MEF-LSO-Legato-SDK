# ServiceApi

All URIs are relative to *https://mef.net:8443/mefApi/legato/serviceInventory/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**serviceFind**](ServiceApi.md#serviceFind) | **GET** /service | List services
[**serviceGet**](ServiceApi.md#serviceGet) | **GET** /service/{id} | Retrieve a service


<a name="serviceFind"></a>
# **serviceFind**
> List serviceFind(relatedPartyPeriodid, serviceSpecificationPeriodid, serviceSpecificationPeriodname, fields, offset, limit)

List services

    This operation list service entities.  Attribute selection is restricted.  fields attribute may be used to filter retrieved attribute(s) for each service

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **relatedPartyPeriodid** | **String**|  | [optional] [default to null]
 **serviceSpecificationPeriodid** | **String**|  | [optional] [default to null]
 **serviceSpecificationPeriodname** | **String**|  | [optional] [default to null]
 **fields** | **String**| Comma-separated properties of the Service instance to be included  in the returned response | [optional] [default to null]
 **offset** | **Integer**| Requested start index in a ordered list (sorted by id property) of  matching Service instances to be provided in response.  | [optional] [default to null]
 **limit** | **Integer**| Requested maximum number of Service instances to be provided  in the response | [optional] [default to null]

### Return type

[**List**](../\Models/Service.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json;charset=utf-8

<a name="serviceGet"></a>
# **serviceGet**
> Service serviceGet(id, fields)

Retrieve a service

    This operation retrieves a service entity.  Attribute selection is enabled for all first level attributes.

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **String**| Identifier of the Service instance | [default to null]
 **fields** | **String**| Comma-separated properties of the Service instance to be included  in the returned response | [optional] [default to null]

### Return type

[**Service**](../\Models/Service.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json;charset=utf-8

