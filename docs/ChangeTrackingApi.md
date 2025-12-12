# whisper_api_sdk.ChangeTrackingApi

All URIs are relative to *https://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_changes**](ChangeTrackingApi.md#get_changes) | **GET** /v1/ops/tracking/{type}/{value} | Get Detected Changes
[**list_tracked_indicators**](ChangeTrackingApi.md#list_tracked_indicators) | **GET** /v1/ops/tracking | List Tracked Indicators
[**start_change_tracking**](ChangeTrackingApi.md#start_change_tracking) | **POST** /v1/ops/tracking/{type}/{value} | Start Change Tracking
[**stop_change_tracking**](ChangeTrackingApi.md#stop_change_tracking) | **DELETE** /v1/ops/tracking/{type}/{value} | Stop Change Tracking
[**trigger_check**](ChangeTrackingApi.md#trigger_check) | **POST** /v1/ops/tracking/{type}/{value}/check | Trigger Immediate Check


# **get_changes**
> ChangeTrackingResponse get_changes(type, value, since=since)

Get Detected Changes

<p>Retrieve detected changes for a tracked indicator. Returns the current tracking configuration,
baseline snapshot, and list of all detected changes.</p>
<h4>Response Includes:</h4>
<ul>
    <li><b>tracking:</b> Current tracking configuration (enabled, frequency, fields, next check)</li>
    <li><b>baseline:</b> The stored baseline snapshot data</li>
    <li><b>changes:</b> Array of detected changes with timestamps, old/new values</li>
    <li><b>totalChanges:</b> Total number of changes detected</li>
</ul>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.change_tracking_response import ChangeTrackingResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "https://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API Key): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.ChangeTrackingApi(api_client)
    type = 'domain' # str | Indicator type: ip or domain
    value = 'google.com' # str | Indicator value
    since = '2025-01-01T00:00:00Z' # str | ISO 8601 timestamp to get changes from (optional)

    try:
        # Get Detected Changes
        api_response = api_instance.get_changes(type, value, since=since)
        print("The response of ChangeTrackingApi->get_changes:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ChangeTrackingApi->get_changes: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| Indicator type: ip or domain | 
 **value** | **str**| Indicator value | 
 **since** | **str**| ISO 8601 timestamp to get changes from | [optional] 

### Return type

[**ChangeTrackingResponse**](ChangeTrackingResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successfully retrieved changes. |  -  |
**404** | Indicator is not being tracked. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_tracked_indicators**
> TrackedIndicatorsResponse list_tracked_indicators()

List Tracked Indicators

<p>Get a list of all indicators currently being tracked for changes by the authenticated user.</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.tracked_indicators_response import TrackedIndicatorsResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "https://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API Key): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.ChangeTrackingApi(api_client)

    try:
        # List Tracked Indicators
        api_response = api_instance.list_tracked_indicators()
        print("The response of ChangeTrackingApi->list_tracked_indicators:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ChangeTrackingApi->list_tracked_indicators: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**TrackedIndicatorsResponse**](TrackedIndicatorsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of tracked indicators. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **start_change_tracking**
> JobResponse start_change_tracking(type, value, change_tracking_request)

Start Change Tracking

<p>Start tracking changes for an IP or domain. When tracking is started, a baseline snapshot is captured.
Subsequent checks will compare against this baseline and record any detected changes.</p>
<h4>Trackable Fields for Domains:</h4>
<ul>
    <li><b>dns:</b> A, AAAA, MX, NS, TXT, CNAME records</li>
    <li><b>whois:</b> Registrant, registrar, dates, nameservers</li>
    <li><b>ssl:</b> Certificate issuer, expiry, SAN</li>
    <li><b>subdomains:</b> Discovered subdomains</li>
    <li><b>ips:</b> Resolved IP addresses</li>
</ul>
<h4>Trackable Fields for IPs:</h4>
<ul>
    <li><b>geolocation:</b> Country, city, coordinates</li>
    <li><b>asn:</b> ASN number, organization</li>
    <li><b>routing:</b> BGP routing status</li>
    <li><b>rpki:</b> RPKI validation status</li>
    <li><b>reverse_dns:</b> PTR records</li>
</ul>
<h4>Frequencies:</h4>
<ul>
    <li><b>hourly:</b> Check every hour</li>
    <li><b>daily:</b> Check once per day (default)</li>
    <li><b>weekly:</b> Check once per week</li>
</ul>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.change_tracking_request import ChangeTrackingRequest
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "https://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API Key): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.ChangeTrackingApi(api_client)
    type = 'domain' # str | Indicator type: ip or domain
    value = 'google.com' # str | Indicator value (IP address or domain name)
    change_tracking_request = whisper_api_sdk.ChangeTrackingRequest() # ChangeTrackingRequest | Tracking configuration

    try:
        # Start Change Tracking
        api_response = api_instance.start_change_tracking(type, value, change_tracking_request)
        print("The response of ChangeTrackingApi->start_change_tracking:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ChangeTrackingApi->start_change_tracking: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| Indicator type: ip or domain | 
 **value** | **str**| Indicator value (IP address or domain name) | 
 **change_tracking_request** | [**ChangeTrackingRequest**](ChangeTrackingRequest.md)| Tracking configuration | 

### Return type

[**JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**202** | Tracking started. Job ID returned for baseline capture. |  -  |
**400** | Invalid indicator type or fields. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **stop_change_tracking**
> GenericSuccessResponse stop_change_tracking(type, value, delete_history=delete_history)

Stop Change Tracking

<p>Stop tracking changes for an indicator. Optionally delete all change history.</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.generic_success_response import GenericSuccessResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "https://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API Key): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.ChangeTrackingApi(api_client)
    type = 'type_example' # str | Indicator type: ip or domain
    value = 'value_example' # str | Indicator value
    delete_history = False # bool | Delete change history as well (optional) (default to False)

    try:
        # Stop Change Tracking
        api_response = api_instance.stop_change_tracking(type, value, delete_history=delete_history)
        print("The response of ChangeTrackingApi->stop_change_tracking:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ChangeTrackingApi->stop_change_tracking: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| Indicator type: ip or domain | 
 **value** | **str**| Indicator value | 
 **delete_history** | **bool**| Delete change history as well | [optional] [default to False]

### Return type

[**GenericSuccessResponse**](GenericSuccessResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Tracking stopped successfully. |  -  |
**401** | Authentication failed. |  -  |
**500** | Internal server error. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **trigger_check**
> GenericSuccessResponse trigger_check(type, value)

Trigger Immediate Check

<p>Trigger an immediate check for changes on a tracked indicator. Creates a job to compare
current data against the stored baseline.</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.generic_success_response import GenericSuccessResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "https://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (API Key): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.ChangeTrackingApi(api_client)
    type = 'domain' # str | Indicator type
    value = 'google.com' # str | Indicator value

    try:
        # Trigger Immediate Check
        api_response = api_instance.trigger_check(type, value)
        print("The response of ChangeTrackingApi->trigger_check:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ChangeTrackingApi->trigger_check: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| Indicator type | 
 **value** | **str**| Indicator value | 

### Return type

[**GenericSuccessResponse**](GenericSuccessResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**202** | Check triggered successfully. |  -  |
**400** | Invalid indicator type. |  -  |
**404** | Indicator is not being tracked. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

