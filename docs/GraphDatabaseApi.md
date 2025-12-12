# whisper_api_sdk.GraphDatabaseApi

All URIs are relative to *https://api.whisper.security*

Method | HTTP request | Description
------------- | ------------- | -------------
[**execute_cypher_query**](GraphDatabaseApi.md#execute_cypher_query) | **POST** /v1/ops/graph/cypher | Execute Cypher Query
[**execute_graph_ql**](GraphDatabaseApi.md#execute_graph_ql) | **POST** /v1/ops/graph/graphql | Execute GraphQL Query
[**get_graphi_ql**](GraphDatabaseApi.md#get_graphi_ql) | **GET** /v1/ops/graph/graphiql | GraphiQL Interactive Explorer
[**get_health**](GraphDatabaseApi.md#get_health) | **GET** /v1/ops/graph/health | Graph Database Health Check
[**get_schema**](GraphDatabaseApi.md#get_schema) | **GET** /v1/ops/graph/schema | Get Graph Schema


# **execute_cypher_query**
> CypherQueryResponse execute_cypher_query(authorization, cypher_query_request)

Execute Cypher Query

Execute a read-only Cypher query against the FalkorDB graph database.

**Security:** Only read operations (MATCH, RETURN) are allowed.
Write operations are blocked.

**Example Queries:**
```cypher
// Find all IPs for a domain
MATCH (d:DomainName {name: $domain})-[:hasIP]->(ip:A_ADDRESS)
RETURN ip.name AS ip

// Find domains on blocklists
MATCH (d:DomainName)-[:isListed]->(l:LIST)
RETURN d.name, l.name LIMIT 10

// Get ASN and announced prefixes
MATCH (asn:ASN {number: 15169})-[:announces]->(p:ANNOUNCED_PREFIX_4)
RETURN p.name AS prefix
```

**Performance Tips:**
- Always use LIMIT to restrict result size
- Use parameters for variable values
- Filter early in the query with WHERE clauses


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.cypher_query_request import CypherQueryRequest
from whisper_api_sdk.models.cypher_query_response import CypherQueryResponse
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
    api_instance = whisper_api_sdk.GraphDatabaseApi(api_client)
    authorization = 'authorization_example' # str | 
    cypher_query_request = whisper_api_sdk.CypherQueryRequest() # CypherQueryRequest | 

    try:
        # Execute Cypher Query
        api_response = api_instance.execute_cypher_query(authorization, cypher_query_request)
        print("The response of GraphDatabaseApi->execute_cypher_query:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling GraphDatabaseApi->execute_cypher_query: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **str**|  | 
 **cypher_query_request** | [**CypherQueryRequest**](CypherQueryRequest.md)|  | 

### Return type

[**CypherQueryResponse**](CypherQueryResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Query executed successfully |  -  |
**400** | Invalid query syntax |  -  |
**401** | Authentication required |  -  |
**500** | Query execution failed |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **execute_graph_ql**
> execute_graph_ql(authorization, graph_ql_request)

Execute GraphQL Query

Execute a GraphQL query against the graph database.

GraphQL provides a type-safe, structured alternative to Cypher
for querying the graph data.

**Available Query Operations:**
- `domain(name: String!)` - Look up domain information
- `ipv4(address: String!)` - Look up IPv4 address information
- `ipv6(address: String!)` - Look up IPv6 address information
- `asn(number: Int!)` - Look up ASN information
- `searchDomains(pattern: String!, limit: Int)` - Search domains by pattern
- `domainsOnIP(address: String!)` - Find domains on an IP
- `domainsOnASN(asnNumber: Int!, limit: Int)` - Find domains on an ASN
- `checkIndicator(indicator: String!)` - Check if indicator is listed

**Example Query:**
```graphql
{
  domain(name: "google.com") {
    name
    ipAddresses {
      address
      country { code }
    }
    nameservers { name }
    asns { number }
  }
}
```

Use the `/v1/ops/graph/graphiql` endpoint for an interactive
query explorer with schema documentation.


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.graph_ql_request import GraphQLRequest
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
    api_instance = whisper_api_sdk.GraphDatabaseApi(api_client)
    authorization = 'authorization_example' # str | 
    graph_ql_request = whisper_api_sdk.GraphQLRequest() # GraphQLRequest | 

    try:
        # Execute GraphQL Query
        api_instance.execute_graph_ql(authorization, graph_ql_request)
    except Exception as e:
        print("Exception when calling GraphDatabaseApi->execute_graph_ql: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **str**|  | 
 **graph_ql_request** | [**GraphQLRequest**](GraphQLRequest.md)|  | 

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
**200** | Query executed successfully |  -  |
**400** | Invalid query syntax |  -  |
**401** | Authentication required |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_graphi_ql**
> get_graphi_ql()

GraphiQL Interactive Explorer

Access the GraphiQL interactive query explorer.

GraphiQL provides:
- Interactive query editor with syntax highlighting
- Auto-complete for types and fields
- Schema documentation browser
- Query history

**No authentication required** - the UI itself is public,
but queries still require a valid API key.


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
    api_instance = whisper_api_sdk.GraphDatabaseApi(api_client)

    try:
        # GraphiQL Interactive Explorer
        api_instance.get_graphi_ql()
    except Exception as e:
        print("Exception when calling GraphDatabaseApi->get_graphi_ql: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

void (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/html

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | GraphiQL HTML page |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_health**
> object get_health()

Graph Database Health Check

Check the health and connectivity of the graph database.

**No authentication required** - this is a public health endpoint.

Returns database status, connection info, and basic statistics.


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
    api_instance = whisper_api_sdk.GraphDatabaseApi(api_client)

    try:
        # Graph Database Health Check
        api_response = api_instance.get_health()
        print("The response of GraphDatabaseApi->get_health:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling GraphDatabaseApi->get_health: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

**object**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Health status retrieved |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_schema**
> CypherSchemaResponse get_schema(authorization)

Get Graph Schema

Retrieve the graph database schema including available node labels,
relationship types, and their properties.

Use this to discover what data is available for querying before
writing Cypher or GraphQL queries.

**Response includes:**
- Node labels (e.g., DomainName, A_ADDRESS, ASN)
- Relationship types (e.g., hasIP, isListed, announces)
- Properties available on each node and relationship type
- Graph statistics (node and relationship counts)


### Example

* Bearer (API Key) Authentication (bearerAuth):

```python
import whisper_api_sdk
from whisper_api_sdk.models.cypher_schema_response import CypherSchemaResponse
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
    api_instance = whisper_api_sdk.GraphDatabaseApi(api_client)
    authorization = 'authorization_example' # str | 

    try:
        # Get Graph Schema
        api_response = api_instance.get_schema(authorization)
        print("The response of GraphDatabaseApi->get_schema:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling GraphDatabaseApi->get_schema: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **authorization** | **str**|  | 

### Return type

[**CypherSchemaResponse**](CypherSchemaResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Schema retrieved successfully |  -  |
**401** | Authentication required |  -  |
**500** | Failed to retrieve schema |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

