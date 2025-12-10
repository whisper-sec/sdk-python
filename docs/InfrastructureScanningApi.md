# whisper_api_sdk.InfrastructureScanningApi

All URIs are relative to *https://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_infrastructure_map**](InfrastructureScanningApi.md#create_infrastructure_map) | **POST** /v1/ops/scans/map | Map Infrastructure Relationships (Asynchronous)
[**create_infrastructure_scan**](InfrastructureScanningApi.md#create_infrastructure_scan) | **POST** /v1/ops/scans/infrastructure | Infrastructure Security Scan (Asynchronous)


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

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.infrastructure_map_request import InfrastructureMapRequest
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
    api_instance = whisper_api_sdk.InfrastructureScanningApi(api_client)
    infrastructure_map_request = whisper_api_sdk.InfrastructureMapRequest() # InfrastructureMapRequest | Mapping configuration. Example: ```json {   \"startPoint\": \"example.com\",   \"depth\": 2 } ``` 

    try:
        # Map Infrastructure Relationships (Asynchronous)
        api_response = api_instance.create_infrastructure_map(infrastructure_map_request)
        print("The response of InfrastructureScanningApi->create_infrastructure_map:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling InfrastructureScanningApi->create_infrastructure_map: %s\n" % e)
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
**400** | Invalid starting point or depth (must be 1-3). |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_infrastructure_scan**
> JobResponse create_infrastructure_scan(scan_request)

Infrastructure Security Scan (Asynchronous)

<p>Initiates a security scan of a domain's infrastructure. Performs reconnaissance and configuration analysis.</p>
<h4>Scan Types:</h4>
<ul>
    <li><b>comprehensive:</b> Full scan including all modules (subdomains, dns, ssl, technologies, whois)</li>
    <li><b>subdomains:</b> Subdomain enumeration and discovery</li>
    <li><b>ssl:</b> SSL/TLS certificate analysis (issuer, validity, expiration, protocol)</li>
    <li><b>dns:</b> DNS record analysis and configuration</li>
    <li><b>technologies:</b> Technology stack detection via headers and NoctisEyes scan</li>
    <li><b>whois:</b> Domain registration and ownership information</li>
    <li><b>vulnerability:</b> Dedicated vulnerability scan using NoctisEyes (detects security misconfigurations, exposed services, known CVEs)</li>
</ul>
<h4>Performance:</h4>
<ul>
    <li><b>Quick scans:</b> 10-30 seconds (ssl, dns, whois)</li>
    <li><b>Medium scans:</b> 30-60 seconds (subdomains)</li>
    <li><b>Technologies scan:</b> 2-5 minutes (includes NoctisEyes vulnerability scan)</li>
    <li><b>Vulnerability scan:</b> 2-5 minutes (dedicated NoctisEyes security scan with severity breakdown)</li>
    <li><b>Comprehensive scan:</b> 3-5 minutes (all modules in parallel)</li>
</ul>
<h4>Use Cases:</h4>
<ul>
    <li>Pre-engagement reconnaissance for penetration testing</li>
    <li>Attack surface assessment</li>
    <li>SSL certificate monitoring</li>
    <li>Infrastructure inventory</li>
    <li>Vulnerability assessment and security audits</li>
</ul>


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.models.scan_request import ScanRequest
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
    api_instance = whisper_api_sdk.InfrastructureScanningApi(api_client)
    scan_request = whisper_api_sdk.ScanRequest() # ScanRequest | Scan configuration including target domain and scan type.

    try:
        # Infrastructure Security Scan (Asynchronous)
        api_response = api_instance.create_infrastructure_scan(scan_request)
        print("The response of InfrastructureScanningApi->create_infrastructure_scan:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling InfrastructureScanningApi->create_infrastructure_scan: %s\n" % e)
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
**400** | Invalid domain or scan type. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

