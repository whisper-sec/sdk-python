# whisper_api_sdk.LocationApi

All URIs are relative to *https://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_bulk_ip_location**](LocationApi.md#get_bulk_ip_location) | **POST** /v1/location/ips/bulk | Bulk IP Geolocation Lookup
[**get_ip_location**](LocationApi.md#get_ip_location) | **GET** /v1/location/ip/{ip} | Get IP Geolocation and ASN Data
[**get_location_stats**](LocationApi.md#get_location_stats) | **GET** /v1/location/stats | Get Geolocation Database Statistics
[**get_network_location**](LocationApi.md#get_network_location) | **GET** /v1/location/network/{network} | Get Network/CIDR Geolocation Data
[**search_location**](LocationApi.md#search_location) | **GET** /v1/location/search | Search Geolocation Database by Field


# **get_bulk_ip_location**
> get_bulk_ip_location(request_body)

Bulk IP Geolocation Lookup

<p>Retrieve geolocation data for up to 1000 IP addresses in a single request. Optimized for batch processing with parallel lookups.</p>
<h4>Request Format:</h4>
<p>Send a JSON array of IP addresses (IPv4 or IPv6):</p>
<pre><code>["8.8.8.8", "1.1.1.1", "208.67.222.222"]</code></pre>
<h4>Performance:</h4>
<ul>
    <li><b>Response Time:</b> 500-2000ms for typical batches (10-100 IPs)</li>
    <li><b>Processing:</b> Parallel lookups with automatic batching</li>
    <li><b>Limit:</b> Maximum 1000 IPs per request</li>
    <li><b>Rate Limit:</b> 10 requests per minute</li>
</ul>
<h4>Response Format:</h4>
<p>Returns an array of geolocation objects matching the order of input IPs. Failed lookups are indicated with error objects.</p>
<h4>Use Cases:</h4>
<ul>
    <li>Batch enrichment of access logs</li>
    <li>Bulk fraud scoring</li>
    <li>Geographic distribution analysis</li>
    <li>Network infrastructure mapping</li>
</ul>


### Example

* Bearer (API-KEY) Authentication (bearerAuth):

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

# Configure Bearer authorization (API-KEY): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.LocationApi(api_client)
    request_body = ['request_body_example'] # List[str] | JSON array of IP addresses to lookup. Maximum 1000 IPs per request.

    try:
        # Bulk IP Geolocation Lookup
        api_instance.get_bulk_ip_location(request_body)
    except Exception as e:
        print("Exception when calling LocationApi->get_bulk_ip_location: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **request_body** | [**List[str]**](str.md)| JSON array of IP addresses to lookup. Maximum 1000 IPs per request. | 

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**429** | Rate limit exceeded for bulk operations. |  -  |
**200** | Successfully retrieved bulk geolocation data. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |
**400** | Invalid request format. Expected JSON array of IP addresses, or array exceeds 1000 IP limit. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_ip_location**
> get_ip_location(ip)

Get IP Geolocation and ASN Data

<p>Returns comprehensive geolocation and network information for any IPv4 or IPv6 address. This is one of the fastest endpoints in the API, optimized for real-time fraud detection and access control.</p>
<h4>Data Included:</h4>
<ul>
    <li><b>Geographic:</b> Country, city, region, postal code, coordinates, timezone</li>
    <li><b>Network:</b> ASN, ISP/organization name, network range</li>
    <li><b>Classification:</b> Connection type (residential, datacenter, VPN, proxy, hosting)</li>
    <li><b>Reputation:</b> Risk indicators and abuse scores</li>
</ul>
<h4>Performance:</h4>
<ul>
    <li><b>Response Time:</b> Typically &lt;150ms</li>
    <li><b>Cache:</b> Results cached for 6 hours by default</li>
</ul>
<h4>Use Cases:</h4>
<ul>
    <li>Real-time fraud detection in payment flows</li>
    <li>Geographic access control and compliance</li>
    <li>Bot and VPN detection</li>
    <li>Threat intelligence enrichment</li>
</ul>


### Example

* Bearer (API-KEY) Authentication (bearerAuth):

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

# Configure Bearer authorization (API-KEY): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.LocationApi(api_client)
    ip = '8.8.8.8' # str | The IPv4 or IPv6 address to lookup.

    try:
        # Get IP Geolocation and ASN Data
        api_instance.get_ip_location(ip)
    except Exception as e:
        print("Exception when calling LocationApi->get_ip_location: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ip** | **str**| The IPv4 or IPv6 address to lookup. | 

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
**404** | IP address not found in geolocation database. |  -  |
**429** | Rate limit exceeded. |  -  |
**400** | Invalid IP address format. |  -  |
**200** | Successfully retrieved geolocation data. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_location_stats**
> get_location_stats()

Get Geolocation Database Statistics

<p>Returns metadata and statistics about the geolocation database, including coverage, update frequency, and data quality metrics.</p>
<h4>Statistics Included:</h4>
<ul>
    <li><b>Coverage:</b> Total IP addresses, networks, and ASNs covered</li>
    <li><b>Geographic:</b> Number of countries, cities, and regions</li>
    <li><b>Freshness:</b> Last update timestamp and update frequency</li>
    <li><b>Data Sources:</b> Providers and data collection methods</li>
    <li><b>Accuracy:</b> Quality metrics and confidence scores</li>
</ul>
<h4>Use Cases:</h4>
<ul>
    <li>Verifying database coverage for your use case</li>
    <li>Monitoring data freshness</li>
    <li>Understanding data quality and accuracy</li>
</ul>


### Example

* Bearer (API-KEY) Authentication (bearerAuth):

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

# Configure Bearer authorization (API-KEY): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.LocationApi(api_client)

    try:
        # Get Geolocation Database Statistics
        api_instance.get_location_stats()
    except Exception as e:
        print("Exception when calling LocationApi->get_location_stats: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

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
**200** | Successfully retrieved database statistics. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_network_location**
> get_network_location(network)

Get Network/CIDR Geolocation Data

<p>Returns geolocation and network information for an entire network range specified in CIDR notation. Useful for analyzing network blocks, ranges, and subnets.</p>
<h4>Supported Formats:</h4>
<ul>
    <li><b>IPv4 CIDR:</b> 192.168.1.0/24</li>
    <li><b>IPv6 CIDR:</b> 2001:db8::/32</li>
</ul>
<h4>Data Included:</h4>
<ul>
    <li><b>Network Details:</b> CIDR range, first/last IP, total addresses</li>
    <li><b>Geographic:</b> Country, city, region for the network block</li>
    <li><b>Network:</b> ASN, organization, ISP information</li>
    <li><b>Classification:</b> Network type and usage category</li>
</ul>
<h4>Use Cases:</h4>
<ul>
    <li>Analyzing suspicious network ranges</li>
    <li>Bulk geolocation for network blocks</li>
    <li>Infrastructure mapping and reconnaissance</li>
</ul>


### Example

* Bearer (API-KEY) Authentication (bearerAuth):

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

# Configure Bearer authorization (API-KEY): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.LocationApi(api_client)
    network = '8.8.8.0/24' # str | The network range in CIDR notation (e.g., 192.168.1.0/24 or 2001:db8::/32).

    try:
        # Get Network/CIDR Geolocation Data
        api_instance.get_network_location(network)
    except Exception as e:
        print("Exception when calling LocationApi->get_network_location: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **network** | **str**| The network range in CIDR notation (e.g., 192.168.1.0/24 or 2001:db8::/32). | 

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
**400** | Invalid CIDR format or network specification. |  -  |
**404** | Network not found in geolocation database. |  -  |
**200** | Successfully retrieved network geolocation data. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **search_location**
> search_location(var_field, value, limit=limit)

Search Geolocation Database by Field

<p>Search the geolocation database by specific fields to find all IP addresses matching your criteria. Powerful for threat hunting, infrastructure discovery, and pattern analysis.</p>
<h4>Searchable Fields:</h4>
<ul>
    <li><b>Geographic:</b> city, country, country_code, region, postal_code, continent, continent_code</li>
    <li><b>Network:</b> asn, as_number, organization, isp, isp_name</li>
    <li><b>Coordinates:</b> latitude, longitude</li>
</ul>
<h4>Query Examples:</h4>
<ul>
    <li><b>Find all IPs in a city:</b> field=city&value=London</li>
    <li><b>Find all IPs for an ASN:</b> field=asn&value=15169</li>
    <li><b>Find all IPs for an ISP:</b> field=isp_name&value=Google</li>
    <li><b>Find all IPs in country:</b> field=country_code&value=US</li>
</ul>
<h4>Performance:</h4>
<ul>
    <li><b>Response Time:</b> 200-500ms depending on result size</li>
    <li><b>Rate Limit:</b> 5 searches per minute</li>
</ul>
<h4>Use Cases:</h4>
<ul>
    <li>Infrastructure mapping for threat actors</li>
    <li>Finding all IPs in a specific region for compliance</li>
    <li>Discovering VPN/proxy exit nodes</li>
    <li>Threat hunting by ISP or ASN</li>
</ul>


### Example

* Bearer (API-KEY) Authentication (bearerAuth):

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

# Configure Bearer authorization (API-KEY): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.LocationApi(api_client)
    var_field = 'city' # str | The field to search. Valid fields: city, country, country_code, isp_name, isp, asn, as_number, organization, continent, continent_code, region, postal_code, latitude, longitude
    value = 'San Francisco' # str | The value to search for in the specified field.
    limit = 100 # int | Maximum number of results to return. (optional) (default to 100)

    try:
        # Search Geolocation Database by Field
        api_instance.search_location(var_field, value, limit=limit)
    except Exception as e:
        print("Exception when calling LocationApi->search_location: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **var_field** | **str**| The field to search. Valid fields: city, country, country_code, isp_name, isp, asn, as_number, organization, continent, continent_code, region, postal_code, latitude, longitude | 
 **value** | **str**| The value to search for in the specified field. | 
 **limit** | **int**| Maximum number of results to return. | [optional] [default to 100]

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
**200** | Successfully retrieved search results. |  -  |
**400** | Invalid search field or parameters. |  -  |
**429** | Rate limit exceeded for search operations. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

