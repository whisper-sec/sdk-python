# whisper_api_sdk.ScreenshotsApi

All URIs are relative to *https://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**clear_screenshot_history**](ScreenshotsApi.md#clear_screenshot_history) | **DELETE** /v1/ops/screenshots/schedules/{scheduleId}/history | Clear Screenshot History
[**create_screenshot**](ScreenshotsApi.md#create_screenshot) | **POST** /v1/ops/screenshots/capture | Capture a Website Screenshot (Asynchronous)
[**delete_screenshot_schedule**](ScreenshotsApi.md#delete_screenshot_schedule) | **DELETE** /v1/ops/screenshots/schedules/{scheduleId} | Delete Screenshot Schedule
[**get_screenshot_history**](ScreenshotsApi.md#get_screenshot_history) | **GET** /v1/ops/screenshots/history | Get Screenshot History
[**get_screenshot_schedule**](ScreenshotsApi.md#get_screenshot_schedule) | **GET** /v1/ops/screenshots/schedules/{scheduleId} | Get Screenshot Schedule Details
[**list_screenshot_schedules**](ScreenshotsApi.md#list_screenshot_schedules) | **GET** /v1/ops/screenshots/schedules | List Screenshot Schedules
[**schedule_screenshot**](ScreenshotsApi.md#schedule_screenshot) | **POST** /v1/ops/screenshots/schedule | Schedule Recurring Screenshots (Asynchronous)


# **clear_screenshot_history**
> object clear_screenshot_history(schedule_id)

Clear Screenshot History

<p>Delete all captured screenshots for a schedule while keeping the schedule active.</p>
<p><b>Warning:</b> This action cannot be undone. All screenshots will be permanently deleted.</p>


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
    api_instance = whisper_api_sdk.ScreenshotsApi(api_client)
    schedule_id = 'sched_abc123' # str | The schedule ID

    try:
        # Clear Screenshot History
        api_response = api_instance.clear_screenshot_history(schedule_id)
        print("The response of ScreenshotsApi->clear_screenshot_history:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ScreenshotsApi->clear_screenshot_history: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **schedule_id** | **str**| The schedule ID | 

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
**200** | Screenshot history successfully cleared. |  -  |
**404** | Schedule not found or does not belong to your API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_screenshot**
> JobResponse create_screenshot(screenshot_request)

Capture a Website Screenshot (Asynchronous)

<p>Initiates an asynchronous job to capture a screenshot of a website. Supports various viewport sizes, full-page captures, and JavaScript rendering.</p>
<p><b>Performance Note:</b> A typical screenshot capture takes 10-30 seconds. Poll the `/v1/ops/jobs/{jobId}` endpoint to retrieve the URL of the final image.</p>
<p><b>Output:</b> The job result will contain a URL to download the screenshot image in the specified format (PNG, JPEG, or WebP).</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.models.screenshot_request import ScreenshotRequest
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
    api_instance = whisper_api_sdk.ScreenshotsApi(api_client)
    screenshot_request = whisper_api_sdk.ScreenshotRequest() # ScreenshotRequest | The URL and options for the screenshot capture.

    try:
        # Capture a Website Screenshot (Asynchronous)
        api_response = api_instance.create_screenshot(screenshot_request)
        print("The response of ScreenshotsApi->create_screenshot:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ScreenshotsApi->create_screenshot: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **screenshot_request** | [**ScreenshotRequest**](ScreenshotRequest.md)| The URL and options for the screenshot capture. | 

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
**202** | Screenshot job successfully accepted. |  -  |
**400** | Invalid URL or options provided. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |
**429** | Rate limit exceeded. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_screenshot_schedule**
> object delete_screenshot_schedule(schedule_id)

Delete Screenshot Schedule

<p>Delete a scheduled screenshot configuration and optionally all its captured screenshots.</p>
<p><b>Warning:</b> This action cannot be undone. All associated screenshots will be permanently deleted.</p>


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
    api_instance = whisper_api_sdk.ScreenshotsApi(api_client)
    schedule_id = 'sched_abc123' # str | The schedule ID to delete

    try:
        # Delete Screenshot Schedule
        api_response = api_instance.delete_screenshot_schedule(schedule_id)
        print("The response of ScreenshotsApi->delete_screenshot_schedule:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ScreenshotsApi->delete_screenshot_schedule: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **schedule_id** | **str**| The schedule ID to delete | 

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
**200** | Schedule successfully deleted. |  -  |
**404** | Schedule not found or does not belong to your API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_screenshot_history**
> ScreenshotHistoryResponse get_screenshot_history(target, limit=limit)

Get Screenshot History

<p>Retrieve all previously captured screenshots for a specific URL, ordered by capture time (newest first). Includes download URLs and metadata for each capture.</p>
<h4>Response Includes:</h4>
<ul>
    <li><b>Download URL:</b> Direct link to screenshot image</li>
    <li><b>Capture Time:</b> Timestamp when screenshot was taken</li>
    <li><b>Dimensions:</b> Image width and height</li>
    <li><b>Format:</b> Image format (PNG, JPEG, WebP)</li>
    <li><b>File Size:</b> Size in bytes</li>
</ul>
<h4>Use Cases:</h4>
<ul>
    <li>Review website evolution over time</li>
    <li>Compare screenshots for change detection</li>
    <li>Download historical screenshots for reporting</li>
</ul>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.screenshot_history_response import ScreenshotHistoryResponse
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
    api_instance = whisper_api_sdk.ScreenshotsApi(api_client)
    target = 'example.com' # str | The target domain or URL to retrieve screenshot history for.
    limit = 10 # int | Maximum number of screenshots to return. (optional) (default to 10)

    try:
        # Get Screenshot History
        api_response = api_instance.get_screenshot_history(target, limit=limit)
        print("The response of ScreenshotsApi->get_screenshot_history:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ScreenshotsApi->get_screenshot_history: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **target** | **str**| The target domain or URL to retrieve screenshot history for. | 
 **limit** | **int**| Maximum number of screenshots to return. | [optional] [default to 10]

### Return type

[**ScreenshotHistoryResponse**](ScreenshotHistoryResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successfully retrieved screenshot history. |  -  |
**400** | Invalid URL parameter. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |
**404** | No screenshots found for the specified URL. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_screenshot_schedule**
> ScreenshotSchedule get_screenshot_schedule(schedule_id)

Get Screenshot Schedule Details

<p>Retrieve details for a specific screenshot schedule including configuration and capture history.</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.screenshot_schedule import ScreenshotSchedule
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
    api_instance = whisper_api_sdk.ScreenshotsApi(api_client)
    schedule_id = 'sched_abc123' # str | The schedule ID

    try:
        # Get Screenshot Schedule Details
        api_response = api_instance.get_screenshot_schedule(schedule_id)
        print("The response of ScreenshotsApi->get_screenshot_schedule:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ScreenshotsApi->get_screenshot_schedule: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **schedule_id** | **str**| The schedule ID | 

### Return type

[**ScreenshotSchedule**](ScreenshotSchedule.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successfully retrieved schedule details. |  -  |
**404** | Schedule not found or does not belong to your API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_screenshot_schedules**
> ScreenshotScheduleListResponse list_screenshot_schedules()

List Screenshot Schedules

<p>Retrieve all scheduled screenshot configurations for your API key. Each API key can have a maximum of 3 active schedules.</p>
<h4>Response Includes:</h4>
<ul>
    <li><b>Schedule ID:</b> Unique identifier for the schedule</li>
    <li><b>URL:</b> Target website being captured</li>
    <li><b>Frequency:</b> How often screenshots are taken</li>
    <li><b>Next Capture:</b> When the next screenshot will be taken</li>
    <li><b>Capture Count:</b> Total screenshots taken by this schedule</li>
    <li><b>Status:</b> Whether the schedule is enabled or paused</li>
</ul>
<h4>Limits:</h4>
<ul>
    <li><b>Max Schedules:</b> 3 per API key</li>
    <li><b>Max Screenshots:</b> 50 retained per schedule (oldest deleted automatically)</li>
    <li><b>Schedule Expiration:</b> Schedules auto-expire after 90 days of inactivity</li>
</ul>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.screenshot_schedule_list_response import ScreenshotScheduleListResponse
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
    api_instance = whisper_api_sdk.ScreenshotsApi(api_client)

    try:
        # List Screenshot Schedules
        api_response = api_instance.list_screenshot_schedules()
        print("The response of ScreenshotsApi->list_screenshot_schedules:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ScreenshotsApi->list_screenshot_schedules: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**ScreenshotScheduleListResponse**](ScreenshotScheduleListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successfully retrieved schedule list. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **schedule_screenshot**
> JobResponse schedule_screenshot(screenshot_request)

Schedule Recurring Screenshots (Asynchronous)

<p>Create a recurring job to capture website screenshots at regular intervals. Essential for monitoring website changes, detecting defacements, and tracking competitor updates.</p>
<h4>Schedule Options:</h4>
<ul>
    <li><b>Cron Expression:</b> Full cron syntax support (e.g., `0 0 * * * *` = hourly)</li>
    <li><b>Frequency Presets:</b> hourly, every_6_hours, every_12_hours, twice_daily, daily, weekly, monthly</li>
    <li><b>Timezone:</b> Specify timezone for accurate scheduling (default: UTC)</li>
</ul>
<h4>First Screenshot:</h4>
<p>The <b>first screenshot is captured immediately</b> when a schedule is created. Subsequent screenshots follow the configured schedule. This ensures you have baseline data right away.</p>
<h4>Limits:</h4>
<ul>
    <li><b>Max Schedules:</b> 3 per API key</li>
    <li><b>Max Screenshots:</b> 50 retained per schedule (oldest deleted automatically)</li>
    <li><b>Schedule Expiration:</b> Schedules auto-expire after 90 days of inactivity</li>
    <li><b>Screenshot Retention:</b> Individual screenshots expire after 14 days</li>
</ul>
<h4>Performance:</h4>
<ul>
    <li><b>Setup Time:</b> ~2 seconds to create schedule</li>
    <li><b>First Screenshot:</b> Triggered immediately on schedule creation</li>
    <li><b>Screenshot Time:</b> 10-30 seconds per capture</li>
</ul>
<h4>Use Cases:</h4>
<ul>
    <li>Automated defacement detection</li>
    <li>Compliance monitoring and archival</li>
    <li>Competitor website tracking</li>
    <li>Visual regression testing</li>
</ul>
<h4>Management:</h4>
<p>Use <code>GET /v1/ops/screenshots/schedules</code> to list schedules, <code>DELETE /v1/ops/screenshots/schedules/{id}</code> to delete.</p>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.models.screenshot_request import ScreenshotRequest
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
    api_instance = whisper_api_sdk.ScreenshotsApi(api_client)
    screenshot_request = whisper_api_sdk.ScreenshotRequest() # ScreenshotRequest | Schedule configuration including URL, schedule timing, and screenshot options.

    try:
        # Schedule Recurring Screenshots (Asynchronous)
        api_response = api_instance.schedule_screenshot(screenshot_request)
        print("The response of ScreenshotsApi->schedule_screenshot:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ScreenshotsApi->schedule_screenshot: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **screenshot_request** | [**ScreenshotRequest**](ScreenshotRequest.md)| Schedule configuration including URL, schedule timing, and screenshot options. | 

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
**202** | Schedule successfully created. Poll &#x60;/v1/ops/jobs/{jobId}&#x60; for status. |  -  |
**400** | Invalid schedule configuration or missing required fields. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

