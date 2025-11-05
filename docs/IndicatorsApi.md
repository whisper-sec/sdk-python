# whisper_api_sdk.IndicatorsApi

All URIs are relative to *https://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**bulk_enrichment**](IndicatorsApi.md#bulk_enrichment) | **POST** /v1/indicators/bulk | Bulk Indicator Enrichment (Asynchronous)
[**generate_similar_domains_get**](IndicatorsApi.md#generate_similar_domains_get) | **GET** /v1/indicators/domain/{domain}/similar | Generate Similar Domains - GET (Asynchronous)
[**generate_similar_domains_post**](IndicatorsApi.md#generate_similar_domains_post) | **POST** /v1/indicators/domain/{domain}/similar | Generate Similar Domains - POST (Asynchronous)
[**get_indicator**](IndicatorsApi.md#get_indicator) | **GET** /v1/indicators/{type}/{value} | Enrich a Single Indicator (IP or Domain)
[**get_indicator_graph**](IndicatorsApi.md#get_indicator_graph) | **GET** /v1/indicators/{type}/{value}/graph | Get Infrastructure Relationship Graph
[**get_indicator_history**](IndicatorsApi.md#get_indicator_history) | **GET** /v1/indicators/{type}/{value}/history | Get Historical Data for Indicator
[**get_subdomains**](IndicatorsApi.md#get_subdomains) | **GET** /v1/indicators/domain/{domain}/subdomains | Get Domain Subdomains
[**search_indicators**](IndicatorsApi.md#search_indicators) | **POST** /v1/indicators/search | Search Indicators (Asynchronous)


# **bulk_enrichment**
> JobResponse bulk_enrichment(bulk_request)

Bulk Indicator Enrichment (Asynchronous)

<p>Process multiple indicators (IPs and/or domains) in a single request. This endpoint is optimized for batch processing and can handle up to 100 indicators per request.</p>
<p><b>Performance:</b> Processing time depends on batch size and requested data modules. Expect 5-30 seconds for typical batches.</p>
<p><b>Rate Limits:</b> Limited to 10 requests per minute due to the resource-intensive nature of bulk operations.</p>


### Example

* Bearer (API-KEY) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.bulk_request import BulkRequest
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

# Configure Bearer authorization (API-KEY): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.IndicatorsApi(api_client)
    bulk_request = whisper_api_sdk.BulkRequest() # BulkRequest | List of indicators and processing options.

    try:
        # Bulk Indicator Enrichment (Asynchronous)
        api_response = api_instance.bulk_enrichment(bulk_request)
        print("The response of IndicatorsApi->bulk_enrichment:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling IndicatorsApi->bulk_enrichment: %s\n" % e)
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
**202** | Bulk job successfully accepted for processing. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |
**400** | Invalid request. Empty indicator list or exceeds 100 indicator limit. |  -  |
**429** | Rate limit exceeded for bulk operations. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **generate_similar_domains_get**
> JobResponse generate_similar_domains_get(domain)

Generate Similar Domains - GET (Asynchronous)

<p>Initiates an asynchronous job to generate potential lookalike domains using default options. This GET variant is provided for convenience.</p>
<p>For custom options (algorithms, limits, etc.), use the POST version of this endpoint.</p>
<p>The API immediately returns a `jobId`. Poll the `/v1/ops/jobs/{jobId}` endpoint to get the results when complete.</p>


### Example

* Bearer (API-KEY) Authentication (bearerAuth):

```python
import whisper_api_sdk
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

# Configure Bearer authorization (API-KEY): bearerAuth
configuration = whisper_api_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with whisper_api_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = whisper_api_sdk.IndicatorsApi(api_client)
    domain = 'mybrand.com' # str | The domain to generate variations for.

    try:
        # Generate Similar Domains - GET (Asynchronous)
        api_response = api_instance.generate_similar_domains_get(domain)
        print("The response of IndicatorsApi->generate_similar_domains_get:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling IndicatorsApi->generate_similar_domains_get: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **str**| The domain to generate variations for. | 

### Return type

[**JobResponse**](JobResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**202** | Job successfully accepted for processing. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |
**400** | Invalid domain format in path. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **generate_similar_domains_post**
> JobResponse generate_similar_domains_post(domain, similar_domain_request=similar_domain_request)

Generate Similar Domains - POST (Asynchronous)

<p>Initiates an asynchronous job to generate potential lookalike domains for typosquatting, homoglyph, and brand protection analysis. This is a powerful tool for proactive threat hunting.</p>
<p>Because this can be a long-running process, the API immediately returns a `jobId`. Poll the `/v1/ops/jobs/{jobId}` endpoint to get the results when the job is complete.</p>
<p>Use this POST version to specify custom options like algorithms, limits, or filters.</p>


### Example

* Bearer (API-KEY) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.models.similar_domain_request import SimilarDomainRequest
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
    api_instance = whisper_api_sdk.IndicatorsApi(api_client)
    domain = 'mybrand.com' # str | The domain to generate variations for.
    similar_domain_request = whisper_api_sdk.SimilarDomainRequest() # SimilarDomainRequest | Configuration for the similarity generation. (optional)

    try:
        # Generate Similar Domains - POST (Asynchronous)
        api_response = api_instance.generate_similar_domains_post(domain, similar_domain_request=similar_domain_request)
        print("The response of IndicatorsApi->generate_similar_domains_post:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling IndicatorsApi->generate_similar_domains_post: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **str**| The domain to generate variations for. | 
 **similar_domain_request** | [**SimilarDomainRequest**](SimilarDomainRequest.md)| Configuration for the similarity generation. | [optional] 

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
**202** | Job successfully accepted for processing. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |
**400** | Invalid domain format in path. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_indicator**
> IndicatorResponse get_indicator(type, value, include=include)

Enrich a Single Indicator (IP or Domain)

<p>Retrieves comprehensive intelligence for a single IP address or domain. This is the primary, high-performance endpoint for synchronous enrichment.</p>
<p>It aggregates data from multiple sources, including geolocation, WHOIS, DNS, reputation scoring, and relationship mapping. Use the `include` parameter to request additional, deeper data sets that may have higher latency.</p>
<h4>Performance:</h4>
<ul>
    <li><b>Base Response:</b> Typically under 500ms.</li>
    <li><b>With `include=routing`:</b> First request may take up to 5 seconds; subsequent requests are cached for 5 minutes and respond in &lt;200ms.</li>
    <li><b>With `include=ip_intelligence`:</b> Adds 200-500ms of latency for each IP address resolved from the domain.</li>
</ul>


### Example

* Bearer (API-KEY) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.indicator_response import IndicatorResponse
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
    api_instance = whisper_api_sdk.IndicatorsApi(api_client)
    type = 'ip' # str | The type of indicator to enrich.
    value = '8.8.8.8' # str | The value of the indicator (e.g., an IPv4/IPv6 address or a domain name).
    include = 'routing,whois' # str | A comma-separated list of additional data modules to include in the response. Requesting more modules may increase latency. (optional)

    try:
        # Enrich a Single Indicator (IP or Domain)
        api_response = api_instance.get_indicator(type, value, include=include)
        print("The response of IndicatorsApi->get_indicator:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling IndicatorsApi->get_indicator: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| The type of indicator to enrich. | 
 **value** | **str**| The value of the indicator (e.g., an IPv4/IPv6 address or a domain name). | 
 **include** | **str**| A comma-separated list of additional data modules to include in the response. Requesting more modules may increase latency. | [optional] 

### Return type

[**IndicatorResponse**](IndicatorResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**401** | Authentication failed. Missing or invalid API key. |  -  |
**404** | The requested indicator was not found in our datasets. |  -  |
**429** | Rate limit exceeded. |  -  |
**400** | Invalid indicator format or unsupported type. |  -  |
**200** | Successfully retrieved intelligence data. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_indicator_graph**
> get_indicator_graph(type, value, limit=limit)

Get Infrastructure Relationship Graph

<p>Returns graph visualization data showing relationships between the indicator and related infrastructure. Perfect for interactive network diagrams and threat actor infrastructure mapping.</p>
<h4>Relationship Types Included:</h4>
<ul>
    <li><b>For Domains:</b>
        <ul>
            <li>Resolves to IPs</li>
            <li>Shares nameservers with</li>
            <li>Same SSL certificate as</li>
            <li>Same registrant as</li>
            <li>Links to/from other domains</li>
        </ul>
    </li>
    <li><b>For IPs:</b>
        <ul>
            <li>Hosts domains</li>
            <li>Same ASN as</li>
            <li>Same network block as</li>
            <li>Connected via routing</li>
        </ul>
    </li>
</ul>
<h4>Output Format:</h4>
<p>Compatible with react-force-graph, vis.js, cytoscape.js:</p>
<pre><code>{
  "nodes": [
    {"id": "example.com", "type": "domain", "label": "example.com"},
    {"id": "8.8.8.8", "type": "ip", "label": "8.8.8.8"}
  ],
  "links": [
    {"source": "example.com", "target": "8.8.8.8", "type": "resolves_to"}
  ]
}</code></pre>
<h4>Performance:</h4>
<ul>
    <li>Response Time: 500ms-2s depending on graph complexity</li>
    <li>Default: 100 nodes maximum (adjustable)</li>
</ul>
<h4>Use Cases:</h4>
<ul>
    <li>Interactive threat actor infrastructure visualization</li>
    <li>Discovering related phishing campaigns</li>
    <li>Mapping shadow IT and sprawl</li>
    <li>Network topology visualization</li>
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
    api_instance = whisper_api_sdk.IndicatorsApi(api_client)
    type = 'domain' # str | Type of indicator
    value = 'example.com' # str | The indicator value (IP address or domain)
    limit = 100 # int | Maximum number of nodes to return in the graph (optional) (default to 100)

    try:
        # Get Infrastructure Relationship Graph
        api_instance.get_indicator_graph(type, value, limit=limit)
    except Exception as e:
        print("Exception when calling IndicatorsApi->get_indicator_graph: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| Type of indicator | 
 **value** | **str**| The indicator value (IP address or domain) | 
 **limit** | **int**| Maximum number of nodes to return in the graph | [optional] [default to 100]

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
**404** | Indicator not found or no relationships discovered. |  -  |
**400** | Invalid indicator type or limit parameter. |  -  |
**200** | Successfully retrieved graph data. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_indicator_history**
> HistoryResponse get_indicator_history(type, value, history_type=history_type)

Get Historical Data for Indicator

<p>Retrieves time-series historical data for an IP address or domain. Track how infrastructure changes over time for threat intelligence and forensic analysis.</p>
<h4>History Types:</h4>
<ul>
    <li><b>whois:</b> Registration history - registrant changes, expiration updates, transfers</li>
    <li><b>routing:</b> BGP routing history - prefix announcements, ASN changes, route hijacks</li>
    <li><b>dns:</b> DNS resolution history - IP address changes, nameserver updates</li>
    <li><b>ssl:</b> Certificate history - cert replacements, CA changes, expiration events</li>
    <li><b>reputation:</b> Risk score history - blacklist appearances, reputation changes</li>
</ul>
<h4>Data Format:</h4>
<p>Timeline with dated snapshots showing what changed and when:</p>
<pre><code>{
  "history": [
    {
      "timestamp": "2025-01-15T10:00:00Z",
      "field": "registrant_company",
      "old_value": "Evil Corp",
      "new_value": "Legitimate LLC"
    }
  ]
}</code></pre>
<h4>Use Cases:</h4>
<ul>
    <li>Tracking domain ownership changes</li>
    <li>Investigating IP reputation degradation</li>
    <li>Forensic timeline reconstruction</li>
    <li>Detecting infrastructure pivots by threat actors</li>
</ul>


### Example

* Bearer (API-KEY) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.history_response import HistoryResponse
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
    api_instance = whisper_api_sdk.IndicatorsApi(api_client)
    type = 'domain' # str | Type of indicator
    value = 'example.com' # str | The indicator value (IP address or domain)
    history_type = 'whois' # str | Type of historical data to retrieve (optional)

    try:
        # Get Historical Data for Indicator
        api_response = api_instance.get_indicator_history(type, value, history_type=history_type)
        print("The response of IndicatorsApi->get_indicator_history:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling IndicatorsApi->get_indicator_history: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| Type of indicator | 
 **value** | **str**| The indicator value (IP address or domain) | 
 **history_type** | **str**| Type of historical data to retrieve | [optional] 

### Return type

[**HistoryResponse**](HistoryResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**401** | Authentication failed. Missing or invalid API key. |  -  |
**400** | Invalid indicator type or history type. |  -  |
**200** | Successfully retrieved historical data. |  -  |
**404** | No historical data found for this indicator. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_subdomains**
> SubdomainResponse get_subdomains(domain, limit=limit)

Get Domain Subdomains

Retrieves a list of discovered subdomains for a given root domain, based on passive DNS and other enumeration techniques.

### Example

* Bearer (API-KEY) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.subdomain_response import SubdomainResponse
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
    api_instance = whisper_api_sdk.IndicatorsApi(api_client)
    domain = 'google.com' # str | The root domain to query for subdomains.
    limit = 100 # int | The maximum number of subdomains to return. (optional) (default to 100)

    try:
        # Get Domain Subdomains
        api_response = api_instance.get_subdomains(domain, limit=limit)
        print("The response of IndicatorsApi->get_subdomains:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling IndicatorsApi->get_subdomains: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **str**| The root domain to query for subdomains. | 
 **limit** | **int**| The maximum number of subdomains to return. | [optional] [default to 100]

### Return type

[**SubdomainResponse**](SubdomainResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**400** | Invalid domain format. |  -  |
**401** | Authentication failed. Missing or invalid API key. |  -  |
**404** | Domain not found or no subdomains discovered. |  -  |
**200** | Successfully retrieved subdomains. |  -  |

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

* Bearer (API-KEY) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.job_response import JobResponse
from whisper_api_sdk.models.search_request import SearchRequest
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
    api_instance = whisper_api_sdk.IndicatorsApi(api_client)
    search_request = whisper_api_sdk.SearchRequest() # SearchRequest | The search query and configuration.

    try:
        # Search Indicators (Asynchronous)
        api_response = api_instance.search_indicators(search_request)
        print("The response of IndicatorsApi->search_indicators:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling IndicatorsApi->search_indicators: %s\n" % e)
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
**401** | Authentication failed. Missing or invalid API key. |  -  |
**400** | Invalid search query or parameters. |  -  |
**429** | Rate limit exceeded for search operations. |  -  |
**202** | Search job successfully accepted. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

