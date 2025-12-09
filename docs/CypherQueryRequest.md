# CypherQueryRequest

Request to execute a read-only Cypher query against the FalkorDB graph database.  **Security Note:** Only read operations (MATCH, RETURN) are allowed. Write operations (CREATE, DELETE, SET, MERGE) are blocked by the backend.  **Example Queries:** - Find domain IPs: `MATCH (d:DomainName {name: $domain})-[:hasIP]->(ip:A_ADDRESS) RETURN ip.name` - Get ASN info: `MATCH (asn:ASN {number: $asn})-[:announces]->(p:ANNOUNCED_PREFIX_4) RETURN p` - Find blacklisted IPs: `MATCH (ip:A_ADDRESS)-[:isListed]->(l:LIST) RETURN ip.name, l.name LIMIT 10` 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | **str** | The Cypher query to execute. Must be a read-only query (MATCH/RETURN).  Use &#x60;$paramName&#x60; syntax to reference parameters from the &#x60;parameters&#x60; map.  | 
**parameters** | **Dict[str, object]** | Query parameters as key-value pairs. Use &#x60;$key&#x60; in the query to reference these.  Supported value types: String, Number, Boolean, List, Map.  | [optional] 
**limit** | **int** | Maximum number of results to return. Overrides any LIMIT clause in the query. | [optional] [default to 100]

## Example

```python
from whisper_api_sdk.models.cypher_query_request import CypherQueryRequest

# TODO update the JSON string below
json = "{}"
# create an instance of CypherQueryRequest from a JSON string
cypher_query_request_instance = CypherQueryRequest.from_json(json)
# print the JSON string representation of the object
print(CypherQueryRequest.to_json())

# convert the object into a dict
cypher_query_request_dict = cypher_query_request_instance.to_dict()
# create an instance of CypherQueryRequest from a dict
cypher_query_request_from_dict = CypherQueryRequest.from_dict(cypher_query_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


