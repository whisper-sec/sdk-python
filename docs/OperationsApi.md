# whisper_api_sdk.OperationsApi

All URIs are relative to *http://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**bulk_enrichment**](OperationsApi.md#bulk_enrichment) | **POST** /v1/ops/enrichment/bulk | Bulk Indicator Enrichment (Asynchronous)
[**create_infrastructure_map**](OperationsApi.md#create_infrastructure_map) | **POST** /v1/ops/scans/map | Map Infrastructure Relationships (Asynchronous)
[**create_infrastructure_scan**](OperationsApi.md#create_infrastructure_scan) | **POST** /v1/ops/scans/infrastructure | Infrastructure Security Scan (Asynchronous)
[**create_monitor_check**](OperationsApi.md#create_monitor_check) | **POST** /v1/ops/monitoring | Create Monitoring Check
[**create_monitoring_alert**](OperationsApi.md#create_monitoring_alert) | **POST** /v1/ops/monitoring/{target}/alert | Configure Monitoring Alerts (Asynchronous)
[**create_screenshot**](OperationsApi.md#create_screenshot) | **POST** /v1/ops/screenshots/capture | Capture a Website Screenshot (Asynchronous)
[**delete_monitor_check**](OperationsApi.md#delete_monitor_check) | **DELETE** /v1/ops/monitoring/{checkId} | Delete Monitoring Check
[**get_changes**](OperationsApi.md#get_changes) | **GET** /v1/ops/tracking/{type}/{value} | Get Detected Changes
[**get_job**](OperationsApi.md#get_job) | **GET** /v1/ops/jobs/{jobId} | Get Asynchronous Job Status and Results
[**get_monitor_check**](OperationsApi.md#get_monitor_check) | **GET** /v1/ops/monitoring/{checkId} | Get Monitoring Check
[**get_monitor_dashboard**](OperationsApi.md#get_monitor_dashboard) | **GET** /v1/ops/monitoring/dashboard | Get Monitoring Dashboard
[**get_monitor_results**](OperationsApi.md#get_monitor_results) | **GET** /v1/ops/monitoring/{checkId}/results | Get Check Results
[**get_monitoring_status**](OperationsApi.md#get_monitoring_status) | **GET** /v1/ops/monitoring/status/{target} | Get Monitoring Status and Metrics
[**get_screenshot_history**](OperationsApi.md#get_screenshot_history) | **GET** /v1/ops/screenshots/history | Get Screenshot History
[**list_jobs**](OperationsApi.md#list_jobs) | **GET** /v1/ops/jobs/list | List Recent Jobs
[**list_monitor_checks**](OperationsApi.md#list_monitor_checks) | **GET** /v1/ops/monitoring | List Monitoring Checks
[**list_tracked_indicators**](OperationsApi.md#list_tracked_indicators) | **GET** /v1/ops/tracking | List Tracked Indicators
[**schedule_screenshot**](OperationsApi.md#schedule_screenshot) | **POST** /v1/ops/screenshots/schedule | Schedule Recurring Screenshots (Asynchronous)
[**search_indicators**](OperationsApi.md#search_indicators) | **POST** /v1/ops/enrichment/search | Search Indicators (Asynchronous)
[**similar_domains**](OperationsApi.md#similar_domains) | **POST** /v1/ops/enrichment/similar-domains | Find Similar Domains (Asynchronous)
[**start_change_tracking**](OperationsApi.md#start_change_tracking) | **POST** /v1/ops/tracking/{type}/{value} | Start Change Tracking
[**stop_change_tracking**](OperationsApi.md#stop_change_tracking) | **DELETE** /v1/ops/tracking/{type}/{value} | Stop Change Tracking
[**trigger_check**](OperationsApi.md#trigger_check) | **POST** /v1/ops/tracking/{type}/{value}/check | Trigger Immediate Check
[**trigger_monitor_check**](OperationsApi.md#trigger_monitor_check) | **POST** /v1/ops/monitoring/{checkId}/trigger | Trigger Manual Check
[**update_monitor_check**](OperationsApi.md#update_monitor_check) | **PUT** /v1/ops/monitoring/{checkId} | Update Monitoring Check


# **bulk_enrichment**
> JobResponse bulk_enrichment(bulk_request)

Bulk Indicator Enrichment (Asynchronous)

<p>Process multiple indicators (IPs and/or domains) in a single request. This endpoint is optimized for batch processing and can handle up to 100 indicators per request.</p>
<p><b>Performance:</b> Processing time depends on batch size and requested data modules. Expect 5-30 seconds for typical batches.</p>
<p><b>Rate Limits:</b> Limited to 10 requests per minute due to the resource-intensive nature of bulk operations.</p>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.bulk_request import BulkRequest
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    bulk_request = whisper_api_sdk.BulkRequest() # BulkRequest | List of indicators and processing options.

    try:
        # Bulk Indicator Enrichment (Asynchronous)
        api_response = api_instance.bulk_enrichment(bulk_request)
        print("The response of OperationsApi->bulk_enrichment:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->bulk_enrichment: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **bulk_request** | [**BulkRequest**](BulkRequest.md)| List of indicators and processing options. | 

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
**400** | Invalid request. Empty indicator list or exceeds 100 indicator limit. |  -  |
**429** | Rate limit exceeded for bulk operations. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |
**202** | Bulk job successfully accepted for processing. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_infrastructure_map**
> JobResponse create_infrastructure_map(infrastructure_map_request)

Map Infrastructure Relationships (Asynchronous)

<p>Creates a comprehensive map of infrastructure relationships starting from a domain or IP. Discovers connected assets through shared hosting, DNS, certificates, and network relationships.</p>
<h4>Mapping Depth Levels:</h4>
<ul>
    <li><b>Depth 1:</b> Direct relationships only (~30 seconds, 10-50 assets)</li>
    <li><b>Depth 2:</b> 2 hops out (~2-5 minutes, 50-500 assets)</li>
    <li><b>Depth 3:</b> 3 hops out (~10-30 minutes, 500-5000 assets)</li>
</ul>
<h4>Relationship Types Discovered:</h4>
<ul>
    <li>Domains on same IP</li>
    <li>Domains sharing nameservers</li>
    <li>Domains with same SSL certificate</li>
    <li>IPs in same ASN</li>
    <li>Domains with same registrant</li>
</ul>
<h4>Output Format:</h4>
<p>Results returned as graph data compatible with visualization libraries (nodes and edges).</p>
<h4>Use Cases:</h4>
<ul>
    <li>Threat actor infrastructure mapping</li>
    <li>Discovering related phishing domains</li>
    <li>Finding shadow IT and forgotten assets</li>
</ul>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.infrastructure_map_request import InfrastructureMapRequest
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    infrastructure_map_request = whisper_api_sdk.InfrastructureMapRequest() # InfrastructureMapRequest | Mapping configuration. Example: ```json {   \"startPoint\": \"example.com\",   \"depth\": 2 } ``` 

    try:
        # Map Infrastructure Relationships (Asynchronous)
        api_response = api_instance.create_infrastructure_map(infrastructure_map_request)
        print("The response of OperationsApi->create_infrastructure_map:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->create_infrastructure_map: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **infrastructure_map_request** | [**InfrastructureMapRequest**](InfrastructureMapRequest.md)| Mapping configuration. Example: &#x60;&#x60;&#x60;json {   \&quot;startPoint\&quot;: \&quot;example.com\&quot;,   \&quot;depth\&quot;: 2 } &#x60;&#x60;&#x60;  | 

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
**202** | Mapping job successfully accepted. Poll &#x60;/v1/ops/jobs/{jobId}&#x60; for results. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |
**400** | Invalid starting point or depth (must be 1-3). |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_infrastructure_scan**
> JobResponse create_infrastructure_scan(scan_request)

Infrastructure Security Scan (Asynchronous)

<p>Initiates a comprehensive security scan of a domain's infrastructure. Performs reconnaissance, port scanning, service detection, and vulnerability assessment.</p>
<h4>Scan Types:</h4>
<ul>
    <li><b>comprehensive:</b> Full scan including all modules (recommended for complete assessment)</li>
    <li><b>subdomains:</b> Subdomain enumeration only</li>
    <li><b>ports:</b> Port scanning and service detection</li>
    <li><b>technologies:</b> Technology stack detection</li>
    <li><b>vulnerabilities:</b> Known vulnerability checks</li>
    <li><b>ssl:</b> SSL/TLS configuration and certificate analysis</li>
    <li><b>dns:</b> DNS configuration and zone transfer tests</li>
    <li><b>whois:</b> Registration and ownership information</li>
</ul>
<h4>Performance:</h4>
<ul>
    <li><b>Quick scans:</b> 30-60 seconds (subdomains, dns, whois)</li>
    <li><b>Comprehensive scan:</b> 5-15 minutes depending on infrastructure size</li>
</ul>
<h4>Use Cases:</h4>
<ul>
    <li>Pre-engagement reconnaissance for penetration testing</li>
    <li>Attack surface assessment</li>
    <li>Infrastructure inventory and mapping</li>
    <li>Vulnerability management</li>
</ul>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.models.scan_request import ScanRequest
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    scan_request = whisper_api_sdk.ScanRequest() # ScanRequest | Scan configuration including target domain and scan type.

    try:
        # Infrastructure Security Scan (Asynchronous)
        api_response = api_instance.create_infrastructure_scan(scan_request)
        print("The response of OperationsApi->create_infrastructure_scan:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->create_infrastructure_scan: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **scan_request** | [**ScanRequest**](ScanRequest.md)| Scan configuration including target domain and scan type. | 

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
**202** | Scan job successfully accepted. Poll &#x60;/v1/ops/jobs/{jobId}&#x60; for results. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |
**400** | Invalid domain or scan type. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

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

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.monitor_check_request import MonitorCheckRequest
from whisper_api_sdk.models.monitor_check_response import MonitorCheckResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    monitor_check_request = whisper_api_sdk.MonitorCheckRequest() # MonitorCheckRequest | Monitoring check configuration

    try:
        # Create Monitoring Check
        api_response = api_instance.create_monitor_check(monitor_check_request)
        print("The response of OperationsApi->create_monitor_check:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->create_monitor_check: %s\n" % e)
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
**401** | Authentication failed. |  -  |
**201** | Monitoring check created successfully. |  -  |
**400** | Invalid request - missing name or URL. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_monitoring_alert**
> JobResponse create_monitoring_alert(target, monitoring_alert_request)

Configure Monitoring Alerts (Asynchronous)

<p>Create alert rules for a monitored asset. Get notified via webhook, email, or Slack when specific conditions are met.</p>
<h4>Alert Types:</h4>
<ul>
    <li><b>downtime:</b> Site becomes unreachable</li>
    <li><b>dns_change:</b> DNS records modified</li>
    <li><b>whois_change:</b> Registration details updated</li>
    <li><b>ssl_expiring:</b> Certificate expires soon (7, 14, 30 days)</li>
    <li><b>content_change:</b> Page content modified</li>
    <li><b>technology_change:</b> Tech stack changes detected</li>
</ul>
<h4>Notification Channels:</h4>
<ul>
    <li>Webhook (POST to your endpoint)</li>
    <li>Email</li>
    <li>Slack</li>
    <li>PagerDuty</li>
</ul>
<h4>Example Configuration:</h4>
<pre><code>{
  "type": "ssl_expiring",
  "threshold_days": 14,
  "channels": ["email", "slack"],
  "email": "alerts@example.com",
  "slack_webhook": "https://hooks.slack.com/..."
}</code></pre>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.models.monitoring_alert_request import MonitoringAlertRequest
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    target = 'example.com' # str | The domain or IP address to configure alerts for.
    monitoring_alert_request = whisper_api_sdk.MonitoringAlertRequest() # MonitoringAlertRequest | Alert configuration including type, thresholds, and notification channels.

    try:
        # Configure Monitoring Alerts (Asynchronous)
        api_response = api_instance.create_monitoring_alert(target, monitoring_alert_request)
        print("The response of OperationsApi->create_monitoring_alert:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->create_monitoring_alert: %s\n" % e)
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
**401** | Authentication failed. Missing or invalid API key. |  -  |
**202** | Alert configuration job accepted. Poll &#x60;/v1/ops/jobs/{jobId}&#x60; for status. |  -  |
**400** | Invalid alert configuration. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_screenshot**
> JobResponse create_screenshot(screenshot_request)

Capture a Website Screenshot (Asynchronous)

<p>Initiates an asynchronous job to capture a screenshot of a website. Supports various viewport sizes, full-page captures, and JavaScript rendering.</p>
<p><b>Performance Note:</b> A typical screenshot capture takes 10-30 seconds. Poll the `/v1/ops/jobs/{jobId}` endpoint to retrieve the URL of the final image.</p>
<p><b>Output:</b> The job result will contain a URL to download the screenshot image in the specified format (PNG, JPEG, or WebP).</p>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.models.screenshot_request import ScreenshotRequest
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    screenshot_request = whisper_api_sdk.ScreenshotRequest() # ScreenshotRequest | The URL and options for the screenshot capture.

    try:
        # Capture a Website Screenshot (Asynchronous)
        api_response = api_instance.create_screenshot(screenshot_request)
        print("The response of OperationsApi->create_screenshot:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->create_screenshot: %s\n" % e)
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

# **delete_monitor_check**
> delete_monitor_check(check_id)

Delete Monitoring Check

Delete a monitoring check and stop all monitoring for the target.

### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    check_id = 'abc123' # str | Check ID

    try:
        # Delete Monitoring Check
        api_instance.delete_monitor_check(check_id)
    except Exception as e:
        print("Exception when calling OperationsApi->delete_monitor_check: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **check_id** | **str**| Check ID | 

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**401** | Authentication failed. |  -  |
**404** | Check not found or access denied. |  -  |
**204** | Check deleted successfully. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

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

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.change_tracking_response import ChangeTrackingResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    type = 'domain' # str | Indicator type: ip or domain
    value = 'google.com' # str | Indicator value
    since = '2025-01-01T00:00:00Z' # str | ISO 8601 timestamp to get changes from (optional)

    try:
        # Get Detected Changes
        api_response = api_instance.get_changes(type, value, since=since)
        print("The response of OperationsApi->get_changes:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->get_changes: %s\n" % e)
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
**401** | Authentication failed. |  -  |
**200** | Successfully retrieved changes. |  -  |
**404** | Indicator is not being tracked. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_job**
> Job get_job(job_id)

Get Asynchronous Job Status and Results

<p>Retrieves the current status and results of an asynchronous job. Poll this endpoint to check job progress.</p>
<h4>Polling Recommendations:</h4>
<ul>
    <li>For fast jobs (e.g., similar domains), poll every 1-2 seconds.</li>
    <li>For slow jobs (e.g., WHOIS search, screenshots), poll every 5-10 seconds.</li>
    <li>Implement an exponential backoff strategy for very long-running jobs.</li>
    <li>Stop polling when the status is `COMPLETED`, `FAILED`, or `CANCELLED`.</li>
</ul>
<h4>Job Statuses:</h4>
<ul>
    <li><b>PENDING:</b> Job is queued and waiting to start.</li>
    <li><b>PROCESSING:</b> Job is actively being processed.</li>
    <li><b>COMPLETED:</b> Job finished successfully, results are available.</li>
    <li><b>FAILED:</b> Job failed with an error.</li>
    <li><b>CANCELLED:</b> Job was cancelled by user or system.</li>
</ul>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job import Job
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    job_id = 'f6250320-9ed4-442b-a389-acfda52d9375' # str | The unique ID of the job, returned from a `POST` operation.

    try:
        # Get Asynchronous Job Status and Results
        api_response = api_instance.get_job(job_id)
        print("The response of OperationsApi->get_job:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->get_job: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **job_id** | **str**| The unique ID of the job, returned from a &#x60;POST&#x60; operation. | 

### Return type

[**Job**](Job.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**404** | Job ID not found. |  -  |
**200** | Job status and results retrieved successfully. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_monitor_check**
> MonitorCheckResponse get_monitor_check(check_id)

Get Monitoring Check

Get details of a specific monitoring check including uptime metrics.

### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.monitor_check_response import MonitorCheckResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    check_id = 'abc123' # str | Check ID

    try:
        # Get Monitoring Check
        api_response = api_instance.get_monitor_check(check_id)
        print("The response of OperationsApi->get_monitor_check:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->get_monitor_check: %s\n" % e)
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
**401** | Authentication failed. |  -  |
**404** | Check not found or access denied. |  -  |

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

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.monitor_dashboard_response import MonitorDashboardResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)

    try:
        # Get Monitoring Dashboard
        api_response = api_instance.get_monitor_dashboard()
        print("The response of OperationsApi->get_monitor_dashboard:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->get_monitor_dashboard: %s\n" % e)
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
**401** | Authentication failed. |  -  |
**200** | Dashboard summary. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_monitor_results**
> get_monitor_results(check_id, limit=limit)

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

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    check_id = 'abc123' # str | Check ID
    limit = 10 # int | Maximum number of results to return (optional) (default to 10)

    try:
        # Get Check Results
        api_instance.get_monitor_results(check_id, limit=limit)
    except Exception as e:
        print("Exception when calling OperationsApi->get_monitor_results: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **check_id** | **str**| Check ID | 
 **limit** | **int**| Maximum number of results to return | [optional] [default to 10]

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**401** | Authentication failed. |  -  |
**404** | Check not found or access denied. |  -  |
**200** | Check execution history. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_monitoring_status**
> get_monitoring_status(target)

Get Monitoring Status and Metrics

<p>Retrieves current monitoring configuration and historical metrics for a domain or IP address.</p>
<h4>Status Information:</h4>
<ul>
    <li><b>Monitoring State:</b> Active, paused, or not monitored</li>
    <li><b>Check Frequency:</b> How often checks are performed</li>
    <li><b>Active Alerts:</b> Currently triggered alert conditions</li>
    <li><b>Last Check:</b> Timestamp of most recent check</li>
</ul>
<h4>Metrics Included:</h4>
<ul>
    <li>Uptime percentage (last 30 days)</li>
    <li>Average response time</li>
    <li>SSL certificate expiration countdown</li>
    <li>DNS change events</li>
    <li>WHOIS change events</li>
</ul>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    target = 'example.com' # str | The domain or IP address to check monitoring status for.

    try:
        # Get Monitoring Status and Metrics
        api_instance.get_monitoring_status(target)
    except Exception as e:
        print("Exception when calling OperationsApi->get_monitoring_status: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **target** | **str**| The domain or IP address to check monitoring status for. | 

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**404** | Target is not being monitored. |  -  |
**200** | Successfully retrieved monitoring status. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_screenshot_history**
> get_screenshot_history(target, limit=limit)

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

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    target = 'example.com' # str | The target domain or URL to retrieve screenshot history for.
    limit = 10 # int | Maximum number of screenshots to return. (optional) (default to 10)

    try:
        # Get Screenshot History
        api_instance.get_screenshot_history(target, limit=limit)
    except Exception as e:
        print("Exception when calling OperationsApi->get_screenshot_history: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **target** | **str**| The target domain or URL to retrieve screenshot history for. | 
 **limit** | **int**| Maximum number of screenshots to return. | [optional] [default to 10]

### Return type

void (empty response body)

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

# **list_jobs**
> list_jobs(status=status, limit=limit, offset=offset)

List Recent Jobs

<p>Retrieves a list of recent jobs for the authenticated user, optionally filtered by status.</p>
<h4>Query Parameters:</h4>
<ul>
    <li><b>status:</b> Filter by job status (PENDING, PROCESSING, COMPLETED, FAILED, CANCELLED)</li>
    <li><b>limit:</b> Maximum number of jobs to return (default: 50, max: 100)</li>
    <li><b>offset:</b> Number of jobs to skip for pagination (default: 0)</li>
</ul>
<h4>Response Format:</h4>
<p>Returns a JSON object with a "jobs" array containing job summaries.</p>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    status = 'status_example' # str | Filter by job status (optional)
    limit = 50 # int | Maximum number of jobs to return (optional) (default to 50)
    offset = 0 # int | Number of jobs to skip (optional) (default to 0)

    try:
        # List Recent Jobs
        api_instance.list_jobs(status=status, limit=limit, offset=offset)
    except Exception as e:
        print("Exception when calling OperationsApi->list_jobs: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **status** | **str**| Filter by job status | [optional] 
 **limit** | **int**| Maximum number of jobs to return | [optional] [default to 50]
 **offset** | **int**| Number of jobs to skip | [optional] [default to 0]

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**401** | Authentication failed. Missing or invalid API key. |  -  |
**200** | Successfully retrieved job list. |  -  |

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

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.monitor_list_response import MonitorListResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    type = 'api' # str | Filter by check type (optional)
    status = 'passing' # str | Filter by status (optional)

    try:
        # List Monitoring Checks
        api_response = api_instance.list_monitor_checks(type=type, status=status)
        print("The response of OperationsApi->list_monitor_checks:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->list_monitor_checks: %s\n" % e)
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

# **list_tracked_indicators**
> list_tracked_indicators()

List Tracked Indicators

<p>Get a list of all indicators currently being tracked for changes by the authenticated user.</p>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)

    try:
        # List Tracked Indicators
        api_instance.list_tracked_indicators()
    except Exception as e:
        print("Exception when calling OperationsApi->list_tracked_indicators: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, */*

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of tracked indicators. |  -  |
**401** | Authentication failed. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **schedule_screenshot**
> JobResponse schedule_screenshot(screenshot_request)

Schedule Recurring Screenshots (Asynchronous)

<p>Create a recurring job to capture website screenshots at regular intervals. Essential for monitoring website changes, detecting defacements, and tracking competitor updates.</p>
<h4>Schedule Options:</h4>
<ul>
    <li><b>Cron Expression:</b> Full cron syntax support (e.g., `0 0 * * * *` = hourly)</li>
    <li><b>Frequency Presets:</b> hourly, daily, weekly, monthly</li>
    <li><b>Timezone:</b> Specify timezone for accurate scheduling</li>
    <li><b>Retention:</b> Auto-cleanup old screenshots (default: keep last 30)</li>
</ul>
<h4>Performance:</h4>
<ul>
    <li><b>Setup Time:</b> ~2 seconds to create schedule</li>
    <li><b>Screenshot Time:</b> 10-30 seconds per capture</li>
</ul>
<h4>Use Cases:</h4>
<ul>
    <li>Automated defacement detection</li>
    <li>Compliance monitoring and archival</li>
    <li>Competitor website tracking</li>
    <li>Visual regression testing</li>
</ul>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.models.screenshot_request import ScreenshotRequest
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    screenshot_request = whisper_api_sdk.ScreenshotRequest() # ScreenshotRequest | Schedule configuration including URL, schedule timing, and screenshot options.

    try:
        # Schedule Recurring Screenshots (Asynchronous)
        api_response = api_instance.schedule_screenshot(screenshot_request)
        print("The response of OperationsApi->schedule_screenshot:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->schedule_screenshot: %s\n" % e)
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
**401** | Authentication failed. Missing or invalid API key. |  -  |
**202** | Schedule successfully created. Poll &#x60;/v1/ops/jobs/{jobId}&#x60; for status. |  -  |
**400** | Invalid schedule configuration or missing required fields. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **search_indicators**
> JobResponse search_indicators(search_request)

Search Indicators (Asynchronous)

<p>Initiates an asynchronous job to search for indicators matching specific criteria. This endpoint is extremely powerful for infrastructure discovery and threat hunting.</p>
<p><b>Performance Note:</b> Searches on WHOIS fields (like `registrantCompany`) are data-intensive and can take over 50 seconds to complete. This endpoint is therefore asynchronous by design. Poll the `/v1/ops/jobs/{jobId}` endpoint to retrieve results.</p>
<h4>Example Search Queries:</h4>
<ul>
    <li>`registrantCompany:EvilCorp` - Find all domains registered by EvilCorp</li>
    <li>`asn:15169` - Find all IPs in Google's ASN</li>
    <li>`city:"San Francisco"` - Find all IPs geolocated to San Francisco</li>
</ul>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.models.search_request import SearchRequest
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    search_request = whisper_api_sdk.SearchRequest() # SearchRequest | The search query and configuration.

    try:
        # Search Indicators (Asynchronous)
        api_response = api_instance.search_indicators(search_request)
        print("The response of OperationsApi->search_indicators:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->search_indicators: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **search_request** | [**SearchRequest**](SearchRequest.md)| The search query and configuration. | 

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
**202** | Search job successfully accepted. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |
**429** | Rate limit exceeded for search operations. |  -  |
**400** | Invalid search query or parameters. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **similar_domains**
> JobResponse similar_domains(similar_domains_ops_request)

Find Similar Domains (Asynchronous)

<p>Generates potential lookalike, typosquatting, and homoglyph domains for brand protection and threat hunting.</p>
<h4>Detection Methods:</h4>
<ul>
    <li>Typosquatting (keyboard proximity)</li>
    <li>Homoglyph attacks (visually similar characters)</li>
    <li>Combosquatting (brand + keyword)</li>
    <li>TLD variations</li>
</ul>
<h4>Performance:</h4>
<p>Typically completes in 5-15 seconds depending on options.</p>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.models.similar_domains_ops_request import SimilarDomainsOpsRequest
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    similar_domains_ops_request = whisper_api_sdk.SimilarDomainsOpsRequest() # SimilarDomainsOpsRequest | Similar domains request with domain and options.

    try:
        # Find Similar Domains (Asynchronous)
        api_response = api_instance.similar_domains(similar_domains_ops_request)
        print("The response of OperationsApi->similar_domains:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->similar_domains: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **similar_domains_ops_request** | [**SimilarDomainsOpsRequest**](SimilarDomainsOpsRequest.md)| Similar domains request with domain and options. | 

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
**400** | Invalid domain or options. |  -  |
**401** | Authentication failed. |  -  |
**202** | Similar domains job created successfully. |  -  |

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

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.change_tracking_request import ChangeTrackingRequest
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    type = 'domain' # str | Indicator type: ip or domain
    value = 'google.com' # str | Indicator value (IP address or domain name)
    change_tracking_request = whisper_api_sdk.ChangeTrackingRequest() # ChangeTrackingRequest | Tracking configuration

    try:
        # Start Change Tracking
        api_response = api_instance.start_change_tracking(type, value, change_tracking_request)
        print("The response of OperationsApi->start_change_tracking:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->start_change_tracking: %s\n" % e)
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
**401** | Authentication failed. |  -  |
**400** | Invalid indicator type or fields. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **stop_change_tracking**
> stop_change_tracking(type, value, delete_history=delete_history)

Stop Change Tracking

<p>Stop tracking changes for an indicator. Optionally delete all change history.</p>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    type = 'type_example' # str | Indicator type: ip or domain
    value = 'value_example' # str | Indicator value
    delete_history = False # bool | Delete change history as well (optional) (default to False)

    try:
        # Stop Change Tracking
        api_instance.stop_change_tracking(type, value, delete_history=delete_history)
    except Exception as e:
        print("Exception when calling OperationsApi->stop_change_tracking: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| Indicator type: ip or domain | 
 **value** | **str**| Indicator value | 
 **delete_history** | **bool**| Delete change history as well | [optional] [default to False]

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**401** | Authentication failed. |  -  |
**204** | Tracking stopped successfully. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **trigger_check**
> JobResponse trigger_check(type, value)

Trigger Immediate Check

<p>Trigger an immediate check for changes on a tracked indicator. Creates a job to compare
current data against the stored baseline.</p>


### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    type = 'type_example' # str | Indicator type
    value = 'value_example' # str | Indicator value

    try:
        # Trigger Immediate Check
        api_response = api_instance.trigger_check(type, value)
        print("The response of OperationsApi->trigger_check:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->trigger_check: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| Indicator type | 
 **value** | **str**| Indicator value | 

### Return type

[**JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*, application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**401** | Authentication failed. |  -  |
**202** | Check triggered. Job ID returned. |  -  |
**404** | Indicator is not being tracked. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **trigger_monitor_check**
> trigger_monitor_check(check_id)

Trigger Manual Check

Trigger an immediate execution of a monitoring check.

### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    check_id = 'abc123' # str | Check ID

    try:
        # Trigger Manual Check
        api_instance.trigger_monitor_check(check_id)
    except Exception as e:
        print("Exception when calling OperationsApi->trigger_monitor_check: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **check_id** | **str**| Check ID | 

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**401** | Authentication failed. |  -  |
**404** | Check not found or access denied. |  -  |
**202** | Check triggered successfully. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_monitor_check**
> MonitorCheckResponse update_monitor_check(check_id, monitor_check_request)

Update Monitoring Check

Update an existing monitoring check configuration.

### Example

* Bearer (JWT) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.monitor_check_request import MonitorCheckRequest
from whisper_api_sdk.models.monitor_check_response import MonitorCheckResponse
from whisper_api_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://api.whisper.security
# See configuration.py for a list of all supported configuration parameters.
configuration = whisper_api_sdk.Configuration(
    host = "http://api.whisper.security"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization (JWT): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.OperationsApi(api_client)
    check_id = 'abc123' # str | Check ID
    monitor_check_request = whisper_api_sdk.MonitorCheckRequest() # MonitorCheckRequest | Updated check configuration

    try:
        # Update Monitoring Check
        api_response = api_instance.update_monitor_check(check_id, monitor_check_request)
        print("The response of OperationsApi->update_monitor_check:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling OperationsApi->update_monitor_check: %s\n" % e)
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
**401** | Authentication failed. |  -  |
**200** | Check updated successfully. |  -  |
**404** | Check not found or access denied. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

