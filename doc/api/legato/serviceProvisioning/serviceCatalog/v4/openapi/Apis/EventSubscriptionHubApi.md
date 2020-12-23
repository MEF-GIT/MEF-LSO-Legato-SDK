# EventSubscriptionHubApi

All URIs are relative to *https://mef.net:8443/mefApi/legato/serviceCatalog/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**hubCreate**](EventSubscriptionHubApi.md#hubCreate) | **POST** /hub | Create Hub
[**hubDelete**](EventSubscriptionHubApi.md#hubDelete) | **DELETE** /hub/{hubId} | Delete Hub
[**hubGet**](EventSubscriptionHubApi.md#hubGet) | **GET** /hub/{hubId} | get hub


<a name="hubCreate"></a>
# **hubCreate**
> EventSubscription hubCreate(eventSubscriptionInput)

Create Hub

    Structure used to create a hub (to subscribe to notification

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **eventSubscriptionInput** | [**EventSubscriptionInput**](../\Models/EventSubscriptionInput.md)|  |

### Return type

[**EventSubscription**](../\Models/EventSubscription.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json;charset=utf-8
- **Accept**: application/json;charset=utf-8

<a name="hubDelete"></a>
# **hubDelete**
> hubDelete(hubId)

Delete Hub

    Delete an existing Hub

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **hubId** | **String**|  | [default to null]

### Return type

null (empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json;charset=utf-8

<a name="hubGet"></a>
# **hubGet**
> EventSubscription hubGet(hubId)

get hub

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **hubId** | **String**|  | [default to null]

### Return type

[**EventSubscription**](../\Models/EventSubscription.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json;charset=utf-8

