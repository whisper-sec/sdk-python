# whisper_api_sdk.MonitoringApi

All URIs are relative to *https://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_monitor_check**](MonitoringApi.md#create_monitor_check) | **POST** /v1/ops/monitoring | Create Monitoring Check
[**create_monitoring_alert**](MonitoringApi.md#create_monitoring_alert) | **POST** /v1/ops/monitoring/{target}/alert | Configure Monitoring Alert
[**delete_monitor_check**](MonitoringApi.md#delete_monitor_check) | **DELETE** /v1/ops/monitoring/{checkId} | Delete Monitoring Check
[**get_monitor_check**](MonitoringApi.md#get_monitor_check) | **GET** /v1/ops/monitoring/{checkId} | Get Monitoring Check
[**get_monitor_dashboard**](MonitoringApi.md#get_monitor_dashboard) | **GET** /v1/ops/monitoring/dashboard | Get Monitoring Dashboard
[**get_monitor_results**](MonitoringApi.md#get_monitor_results) | **GET** /v1/ops/monitoring/{checkId}/results | Get Check Results
[**get_monitoring_status**](MonitoringApi.md#get_monitoring_status) | **GET** /v1/ops/monitoring/status/{target} | Get Monitoring Status
[**list_monitor_checks**](MonitoringApi.md#list_monitor_checks) | **GET** /v1/ops/monitoring | List Monitoring Checks
[**trigger_monitor_check**](MonitoringApi.md#trigger_monitor_check) | **POST** /v1/ops/monitoring/{checkId}/trigger | Trigger Manual Check
[**update_monitor_check**](MonitoringApi.md#update_monitor_check) | **PUT** /v1/ops/monitoring/{checkId} | Update Monitoring Check


# **create_monitor_check**
> MonitorCheckResponse create_monitor_check(monitor_check_request)

Create Monitoring Check

<p>Create a new monitoring check to track uptime and performance of a URL or endpoint.</p>
<h4>Check Types:</h4>
<ul>
    <li><b>api:</b> HTTP/HTTPS endpoint monitoring - checks status code, response time, content</li>
    <li><b>ssl:</b> SSL certificate monitoring - validates certificate and tracks expiry</li>
    <li><b>dns:</b> DNS record monitoring - validates DNS resolution and record values</li>
</ul>
<h4>Frequency Options:</h4>
<p>Check frequency in minutes: 1, 5, 10, 15, 30, 60, 1440 (daily)</p>
<h4>Locations:</h4>
<p>Checks can run from multiple global locations: us-east-1, us-west-1, eu-west-1, ap-southeast-1</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.monitor_check_request import MonitorCheckRequest
from whisper_api_sdk.models.monitor_check_response import MonitorCheckResponse
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
    api_instance = whisper_api_sdk.MonitoringApi(api_client)
    monitor_check_request = whisper_api_sdk.MonitorCheckRequest() # MonitorCheckRequest | Monitoring check configuration

    try:
        # Create Monitoring Check
        api_response = api_instance.create_monitor_check(monitor_check_request)
        print("The response of MonitoringApi->create_monitor_check:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MonitoringApi->create_monitor_check: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **monitor_check_request** | [**MonitorCheckRequest**](MonitorCheckRequest.md)| Monitoring check configuration | 

### Return type

[**MonitorCheckResponse**](MonitorCheckResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Monitoring check created successfully. |  -  |
**400** | Invalid request - missing name or URL. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_monitoring_alert**
> JobResponse create_monitoring_alert(target, monitoring_alert_request)

Configure Monitoring Alert

<p>Configure alert notifications for a monitored target. Set up notifications for downtime, SSL expiry, DNS changes, and more.</p>
<h4>Alert Types:</h4>
<ul>
    <li><b>downtime:</b> Alert when target becomes unreachable</li>
    <li><b>dns_change:</b> Alert when DNS records change</li>
    <li><b>whois_change:</b> Alert when WHOIS data changes</li>
    <li><b>ssl_expiring:</b> Alert when SSL certificate is expiring (within threshold days)</li>
    <li><b>content_change:</b> Alert when page content changes significantly</li>
    <li><b>technology_change:</b> Alert when detected technologies change</li>
</ul>
<h4>Notification Channels:</h4>
<ul>
    <li><b>email:</b> Send alerts via email</li>
    <li><b>slack:</b> Post to Slack webhook</li>
    <li><b>webhook:</b> POST to custom webhook URL</li>
    <li><b>pagerduty:</b> Create PagerDuty incident</li>
</ul>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.models.monitoring_alert_request import MonitoringAlertRequest
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
    api_instance = whisper_api_sdk.MonitoringApi(api_client)
    target = 'example.com' # str | The domain or IP address to configure alerts for.
    monitoring_alert_request = whisper_api_sdk.MonitoringAlertRequest() # MonitoringAlertRequest | Alert configuration including type, thresholds, and notification channels.

    try:
        # Configure Monitoring Alert
        api_response = api_instance.create_monitoring_alert(target, monitoring_alert_request)
        print("The response of MonitoringApi->create_monitoring_alert:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MonitoringApi->create_monitoring_alert: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **target** | **str**| The domain or IP address to configure alerts for. | 
 **monitoring_alert_request** | [**MonitoringAlertRequest**](MonitoringAlertRequest.md)| Alert configuration including type, thresholds, and notification channels. | 

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
**202** | Alert configuration job accepted. |  -  |
**400** | Invalid alert configuration. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_monitor_check**
> object delete_monitor_check(check_id)

Delete Monitoring Check

Delete a monitoring check and stop all monitoring for the target.

### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
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
    api_instance = whisper_api_sdk.MonitoringApi(api_client)
    check_id = 'abc123' # str | Check ID

    try:
        # Delete Monitoring Check
        api_response = api_instance.delete_monitor_check(check_id)
        print("The response of MonitoringApi->delete_monitor_check:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MonitoringApi->delete_monitor_check: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **check_id** | **str**| Check ID | 

### Return type

**object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*, application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Check deleted successfully. |  -  |
**404** | Check not found or access denied. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_monitor_check**
> MonitorCheckResponse get_monitor_check(check_id)

Get Monitoring Check

Get details of a specific monitoring check including uptime metrics.

### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.monitor_check_response import MonitorCheckResponse
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
    api_instance = whisper_api_sdk.MonitoringApi(api_client)
    check_id = 'abc123' # str | Check ID

    try:
        # Get Monitoring Check
        api_response = api_instance.get_monitor_check(check_id)
        print("The response of MonitoringApi->get_monitor_check:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MonitoringApi->get_monitor_check: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **check_id** | **str**| Check ID | 

### Return type

[**MonitorCheckResponse**](MonitorCheckResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Check details. |  -  |
**404** | Check not found or access denied. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_monitor_dashboard**
> MonitorDashboardResponse get_monitor_dashboard()

Get Monitoring Dashboard

<p>Get aggregated dashboard statistics for all monitoring checks.</p>
<h4>Includes:</h4>
<ul>
    <li>Total, passing, failing, and degraded check counts</li>
    <li>Average uptime percentages (24h, 7d, 30d)</li>
    <li>Average response time</li>
    <li>Checks grouped by type and status</li>
</ul>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.monitor_dashboard_response import MonitorDashboardResponse
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
    api_instance = whisper_api_sdk.MonitoringApi(api_client)

    try:
        # Get Monitoring Dashboard
        api_response = api_instance.get_monitor_dashboard()
        print("The response of MonitoringApi->get_monitor_dashboard:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MonitoringApi->get_monitor_dashboard: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**MonitorDashboardResponse**](MonitorDashboardResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Dashboard summary. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_monitor_results**
> MonitorResultListResponse get_monitor_results(check_id, limit=limit)

Get Check Results

<p>Get the execution history for a monitoring check.</p>
<h4>Response includes for each result:</h4>
<ul>
    <li>Timestamp of execution</li>
    <li>Success/failure status</li>
    <li>Response time</li>
    <li>HTTP status code (for API checks)</li>
    <li>Error message (if failed)</li>
</ul>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.monitor_result_list_response import MonitorResultListResponse
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
    api_instance = whisper_api_sdk.MonitoringApi(api_client)
    check_id = 'abc123' # str | Check ID
    limit = 10 # int | Maximum number of results to return (optional) (default to 10)

    try:
        # Get Check Results
        api_response = api_instance.get_monitor_results(check_id, limit=limit)
        print("The response of MonitoringApi->get_monitor_results:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MonitoringApi->get_monitor_results: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **check_id** | **str**| Check ID | 
 **limit** | **int**| Maximum number of results to return | [optional] [default to 10]

### Return type

[**MonitorResultListResponse**](MonitorResultListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Check execution history. |  -  |
**404** | Check not found or access denied. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_monitoring_status**
> MonitoringStatusResponse get_monitoring_status(target)

Get Monitoring Status

<p>Get the current monitoring status and metrics for a domain or IP address.</p>
<h4>Metrics Returned:</h4>
<ul>
    <li>Uptime percentage (last 30 days)</li>
    <li>Average response time</li>
    <li>SSL certificate expiration countdown</li>
    <li>DNS change events</li>
    <li>WHOIS change events</li>
</ul>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.monitoring_status_response import MonitoringStatusResponse
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
    api_instance = whisper_api_sdk.MonitoringApi(api_client)
    target = 'example.com' # str | The domain or IP address to check monitoring status for.

    try:
        # Get Monitoring Status
        api_response = api_instance.get_monitoring_status(target)
        print("The response of MonitoringApi->get_monitoring_status:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MonitoringApi->get_monitoring_status: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **target** | **str**| The domain or IP address to check monitoring status for. | 

### Return type

[**MonitoringStatusResponse**](MonitoringStatusResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successfully retrieved monitoring status. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |
**404** | Target is not being monitored. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_monitor_checks**
> MonitorListResponse list_monitor_checks(type=type, status=status)

List Monitoring Checks

<p>Get a list of all monitoring checks created by the authenticated user.</p>
<h4>Filtering:</h4>
<ul>
    <li><b>type:</b> Filter by check type (api, ssl, dns)</li>
    <li><b>status:</b> Filter by status (passing, failing, degraded, pending)</li>
</ul>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.monitor_list_response import MonitorListResponse
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
    api_instance = whisper_api_sdk.MonitoringApi(api_client)
    type = 'api' # str | Filter by check type (optional)
    status = 'passing' # str | Filter by status (optional)

    try:
        # List Monitoring Checks
        api_response = api_instance.list_monitor_checks(type=type, status=status)
        print("The response of MonitoringApi->list_monitor_checks:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MonitoringApi->list_monitor_checks: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| Filter by check type | [optional] 
 **status** | **str**| Filter by status | [optional] 

### Return type

[**MonitorListResponse**](MonitorListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of monitoring checks. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **trigger_monitor_check**
> GenericSuccessResponse trigger_monitor_check(check_id)

Trigger Manual Check

Trigger an immediate execution of a monitoring check.

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
    api_instance = whisper_api_sdk.MonitoringApi(api_client)
    check_id = 'abc123' # str | Check ID

    try:
        # Trigger Manual Check
        api_response = api_instance.trigger_monitor_check(check_id)
        print("The response of MonitoringApi->trigger_monitor_check:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MonitoringApi->trigger_monitor_check: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **check_id** | **str**| Check ID | 

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
**404** | Check not found or access denied. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_monitor_check**
> MonitorCheckResponse update_monitor_check(check_id, monitor_check_request)

Update Monitoring Check

Update an existing monitoring check configuration.

### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.monitor_check_request import MonitorCheckRequest
from whisper_api_sdk.models.monitor_check_response import MonitorCheckResponse
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
    api_instance = whisper_api_sdk.MonitoringApi(api_client)
    check_id = 'abc123' # str | Check ID
    monitor_check_request = whisper_api_sdk.MonitorCheckRequest() # MonitorCheckRequest | Updated check configuration

    try:
        # Update Monitoring Check
        api_response = api_instance.update_monitor_check(check_id, monitor_check_request)
        print("The response of MonitoringApi->update_monitor_check:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MonitoringApi->update_monitor_check: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **check_id** | **str**| Check ID | 
 **monitor_check_request** | [**MonitorCheckRequest**](MonitorCheckRequest.md)| Updated check configuration | 

### Return type

[**MonitorCheckResponse**](MonitorCheckResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Check updated successfully. |  -  |
**404** | Check not found or access denied. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

