# noctis_frontgraph_sdk.IntelligenceServicesApi

All URIs are relative to *https://spider.noctisnet.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_domain_intelligence**](IntelligenceServicesApi.md#get_domain_intelligence) | **GET** /intelligence/v1/domain/{domain} | Get comprehensive domain intelligence with streaming support
[**get_ip_intelligence**](IntelligenceServicesApi.md#get_ip_intelligence) | **GET** /intelligence/v1/ip/{address} | Get comprehensive IP address intelligence with streaming support


# **get_domain_intelligence**
> DomainIntelligenceResponse get_domain_intelligence(domain)

Get comprehensive domain intelligence with streaming support

Analyzes a domain name and returns comprehensive intelligence data from multiple sources.

**🚀 Response Modes:**
- **Batch Mode** (Default): Complete JSON response in 2-5 seconds
- **Streaming Mode**: Server-Sent Events with 200ms time-to-first-byte
  - Accept: `application/json` for batch mode
  - Accept: `text/event-stream` for streaming mode

**Key Features:**
- WHOIS registration data with ownership history
- Complete DNS record enumeration (A, AAAA, MX, NS, TXT, CNAME, SOA)
- Subdomain discovery and enumeration
- Link analysis showing connected domains
- IP intelligence for all resolved addresses
- Trademark and brand protection status
- Infrastructure relationships and shared hosting

**Streaming Example:**
```bash
curl -N -H 'Accept: text/event-stream' \
     -H 'Authorization: Bearer {token}' \
     https://api.example.com/intelligence/v1/domain/example.com
```

**Streaming Events:**
- `whois`: Domain registration info
- `dns`: DNS records
- `subdomains`: Discovered subdomains
- `ip_intelligence`: Intelligence for each resolved IP
- `complete`: Final aggregated data

**Input Processing:**
- Automatically strips protocols (http://, https://)
- Removes www prefix if present
- Validates domain format before processing

**Note:** Swagger UI only displays batch mode. Use curl or EventSource for streaming.

### Example

* Bearer Authentication (bearerAuth):

```python
import noctis_frontgraph_sdk
from noctis_frontgraph_sdk.models.domain_intelligence_response import DomainIntelligenceResponse
from noctis_frontgraph_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://spider.noctisnet.com
# See configuration.py for a list of all supported configuration parameters.
configuration = noctis_frontgraph_sdk.Configuration(
    host = "https://spider.noctisnet.com"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: bearerAuth
configuration = noctis_frontgraph_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with noctis_frontgraph_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = noctis_frontgraph_sdk.IntelligenceServicesApi(api_client)
    domain = 'domain_example' # str | Domain name to analyze. Can be a root domain or subdomain. Protocol and www prefix are automatically removed.

    try:
        # Get comprehensive domain intelligence with streaming support
        api_response = api_instance.get_domain_intelligence(domain)
        print("The response of IntelligenceServicesApi->get_domain_intelligence:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling IntelligenceServicesApi->get_domain_intelligence: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **domain** | **str**| Domain name to analyze. Can be a root domain or subdomain. Protocol and www prefix are automatically removed. | 

### Return type

[**DomainIntelligenceResponse**](DomainIntelligenceResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Domain intelligence data successfully retrieved |  * X-RateLimit-Limit - Number of requests allowed per hour <br>  |
**400** | Invalid domain name format |  -  |
**401** | Authentication required |  -  |
**404** | Domain not found or unregistered |  -  |
**429** | Rate limit exceeded |  -  |
**500** | Internal server error during intelligence aggregation |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_ip_intelligence**
> IpIntelligenceResponse get_ip_intelligence(address)

Get comprehensive IP address intelligence with streaming support

Analyzes an IP address and returns comprehensive intelligence data aggregated from multiple sources.

**🚀 Response Modes:**
- **Batch Mode** (Default): Complete JSON response in 2-3 seconds
- **Streaming Mode**: Server-Sent Events with 150ms time-to-first-byte
  - Accept: `application/json` for batch mode
  - Accept: `text/event-stream` for streaming mode

**Key Features:**
- Geolocation with city-level precision and confidence scores
- Network topology including ASN, BGP prefixes, and routing visibility
- ISP and organization identification
- DNS relationships showing associated domains
- Risk scoring based on threat intelligence feeds
- RPKI validation and routing security assessment
- Historical routing data and stability metrics

**Streaming Example:**
```bash
curl -N -H 'Accept: text/event-stream' \
     -H 'Authorization: Bearer {token}' \
     https://api.example.com/intelligence/v1/ip/8.8.8.8
```

**Note:** Swagger UI only displays batch mode. Use curl or EventSource for streaming.

### Example

* Bearer Authentication (bearerAuth):

```python
import noctis_frontgraph_sdk
from noctis_frontgraph_sdk.models.ip_intelligence_response import IpIntelligenceResponse
from noctis_frontgraph_sdk.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://spider.noctisnet.com
# See configuration.py for a list of all supported configuration parameters.
configuration = noctis_frontgraph_sdk.Configuration(
    host = "https://spider.noctisnet.com"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: bearerAuth
configuration = noctis_frontgraph_sdk.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with noctis_frontgraph_sdk.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = noctis_frontgraph_sdk.IntelligenceServicesApi(api_client)
    address = 'address_example' # str | IPv4 or IPv6 address to analyze. Supports standard notation (e.g., 192.168.1.1 or 2001:db8::1)

    try:
        # Get comprehensive IP address intelligence with streaming support
        api_response = api_instance.get_ip_intelligence(address)
        print("The response of IntelligenceServicesApi->get_ip_intelligence:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling IntelligenceServicesApi->get_ip_intelligence: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **address** | **str**| IPv4 or IPv6 address to analyze. Supports standard notation (e.g., 192.168.1.1 or 2001:db8::1) | 

### Return type

[**IpIntelligenceResponse**](IpIntelligenceResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | IP intelligence data successfully retrieved |  * X-RateLimit-Limit - Number of requests allowed per hour <br>  * X-RateLimit-Remaining - Number of requests remaining <br>  |
**400** | Invalid IP address format |  -  |
**401** | Authentication required |  -  |
**404** | IP address not found or private/reserved |  -  |
**429** | Rate limit exceeded |  * Retry-After - Number of seconds to wait before retrying <br>  |
**500** | Internal server error during intelligence aggregation |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

