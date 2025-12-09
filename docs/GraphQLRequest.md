# GraphQLRequest

Request to execute a GraphQL query against the graph database.  Follows the standard GraphQL over HTTP specification.  **Available Query Operations:** - `domain(name: String!)` - Look up domain information - `ipv4(address: String!)` - Look up IPv4 address information - `ipv6(address: String!)` - Look up IPv6 address information - `asn(number: Int!)` - Look up ASN information - `searchDomains(pattern: String!, limit: Int)` - Search domains by pattern - `domainsOnIP(address: String!)` - Find domains on an IP - `domainsOnASN(asnNumber: Int!, limit: Int)` - Find domains on an ASN - `checkIndicator(indicator: String!)` - Check if indicator is listed  **Example Query:** ```graphql query GetDomainInfo($domain: String!) {   domain(name: $domain) {     name     ipAddresses {       address       country { code }     }     nameservers { name }     asns { number }   } } ``` 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | **str** | The GraphQL query or mutation to execute | 
**operation_name** | **str** | Name of the operation to execute (for documents with multiple operations) | [optional] 
**variables** | **Dict[str, object]** | Variables to pass to the query as key-value pairs | [optional] 

## Example

```python
from whisper_api_sdk.models.graph_ql_request import GraphQLRequest

# TODO update the JSON string below
json = "{}"
# create an instance of GraphQLRequest from a JSON string
graph_ql_request_instance = GraphQLRequest.from_json(json)
# print the JSON string representation of the object
print(GraphQLRequest.to_json())

# convert the object into a dict
graph_ql_request_dict = graph_ql_request_instance.to_dict()
# create an instance of GraphQLRequest from a dict
graph_ql_request_from_dict = GraphQLRequest.from_dict(graph_ql_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


