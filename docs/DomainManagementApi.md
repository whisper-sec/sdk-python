# noctis_frontgraph_sdk.DomainManagementApi

All URIs are relative to *https://spider.noctisnet.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**find_subdomains**](DomainManagementApi.md#find_subdomains) | **GET** /domainer/api/domains/subdomains/{baseDomain} | Find subdomains


# **find_subdomains**
> DomainerStringListResponse find_subdomains(base_domain, limit=limit, level=level)

Find subdomains

Finds domains that are subdomains of the given base domain (e.g., finding 'www.example.com' for base 'example.com'). Allows filtering by absolute domain level (dot count). NOTE: This differs from relative depth filtering.

### Example

* Bearer Authentication (bearerAuth):

```python
import noctis_frontgraph_sdk
from noctis_frontgraph_sdk.models.domainer_string_list_response import DomainerStringListResponse
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
    api_instance = noctis_frontgraph_sdk.DomainManagementApi(api_client)
    base_domain = 'example.com' # str | Base domain name (e.g., example.com)
    limit = 100 # int | Maximum number of results (optional) (default to 100)
    level = 'ALL' # str | Level of subdomains to find relative to the base domain (ALL, IMMEDIATE=one level deeper, MAX_DEPTH=deepest found relative to base). (optional)

    try:
        # Find subdomains
        api_response = api_instance.find_subdomains(base_domain, limit=limit, level=level)
        print("The response of DomainManagementApi->find_subdomains:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling DomainManagementApi->find_subdomains: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **base_domain** | **str**| Base domain name (e.g., example.com) | 
 **limit** | **int**| Maximum number of results | [optional] [default to 100]
 **level** | **str**| Level of subdomains to find relative to the base domain (ALL, IMMEDIATE&#x3D;one level deeper, MAX_DEPTH&#x3D;deepest found relative to base). | [optional] 

### Return type

[**DomainerStringListResponse**](DomainerStringListResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Subdomains found |  -  |
**400** | Invalid base domain name |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

