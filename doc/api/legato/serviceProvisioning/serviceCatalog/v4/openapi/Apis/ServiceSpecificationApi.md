# ServiceSpecificationApi

All URIs are relative to *https://mef.net:8443/mefApi/legato/serviceCatalog/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**serviceSpecificationFind**](ServiceSpecificationApi.md#serviceSpecificationFind) | **GET** /serviceSpecification | List service specifications
[**serviceSpecificationGet**](ServiceSpecificationApi.md#serviceSpecificationGet) | **GET** /serviceSpecification/{id} | Retrieve a service specification


<a name="serviceSpecificationFind"></a>
# **serviceSpecificationFind**
> List serviceSpecificationFind(category, lifecycleStatus, fields, offset, limit)

List service specifications

    This operation returns service specifications from a catalog

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **category** | **String**| Service Category | [optional] [default to null]
 **lifecycleStatus** | [**ServiceSpecificationState**](../\Models/.md)| Service Specification status | [optional] [default to null] [enum: IN_STUDY, IN_DESIGN, IN_TEST, LAUNCHED, ACTIVE, RETIRED, OBSOLETE, REJECTED]
 **fields** | **String**| Comma-separated properties of the Service Specification to be  included in the returned response | [optional] [default to null]
 **offset** | **Integer**| Requested start index in a ordered list (sorted by id property) of  matching Service Specifications to be provided in response.  | [optional] [default to null]
 **limit** | **Integer**| Requested maximum number of Service Specifications to be provided  in the response | [optional] [default to null]

### Return type

[**List**](../\Models/ServiceSpecification.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json;charset=utf-8

<a name="serviceSpecificationGet"></a>
# **serviceSpecificationGet**
> ServiceSpecification serviceSpecificationGet(id, fields)

Retrieve a service specification

    This operation returns a service specification by its id from a catalog. Attribute selection is enabled using the fields attribute.

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **String**| Identifier of the ServiceSpecification | [default to null]
 **fields** | **String**| Comma-separated properties of the Service Specification to be  included in the returned response | [optional] [default to null]

### Return type

[**ServiceSpecification**](../\Models/ServiceSpecification.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json;charset=utf-8

