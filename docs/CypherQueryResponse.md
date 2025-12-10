# CypherQueryResponse

Response from executing a Cypher query against the graph database.  Contains the query results as a list of records, along with execution metadata including timing and column information. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**results** | **List[Dict[str, object]]** | Query results as a list of records. Each record is a map of column name to value. | [optional] 
**execution_time_ms** | **int** | Query execution time in milliseconds | [optional] 
**row_count** | **int** | Number of rows returned | [optional] 
**columns** | **List[str]** | Column names in the result set | [optional] 
**truncated** | **bool** | Whether the result was truncated due to limit | [optional] 
**error** | **str** | Error message if the query failed | [optional] 

## Example

```python
from whisper_api_sdk.models.cypher_query_response import CypherQueryResponse

# TODO update the JSON string below
json = "{}"
# create an instance of CypherQueryResponse from a JSON string
cypher_query_response_instance = CypherQueryResponse.from_json(json)
# print the JSON string representation of the object
print(CypherQueryResponse.to_json())

# convert the object into a dict
cypher_query_response_dict = cypher_query_response_instance.to_dict()
# create an instance of CypherQueryResponse from a dict
cypher_query_response_from_dict = CypherQueryResponse.from_dict(cypher_query_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


