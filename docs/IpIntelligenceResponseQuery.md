# IpIntelligenceResponseQuery

Query metadata

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ip** | **str** | Queried IP address | [optional] 
**timestamp** | **datetime** | Query timestamp | [optional] 
**response_time_ms** | **int** | Response time in milliseconds | [optional] 

## Example

```python
from noctis_frontgraph_sdk.models.ip_intelligence_response_query import IpIntelligenceResponseQuery

# TODO update the JSON string below
json = "{}"
# create an instance of IpIntelligenceResponseQuery from a JSON string
ip_intelligence_response_query_instance = IpIntelligenceResponseQuery.from_json(json)
# print the JSON string representation of the object
print(IpIntelligenceResponseQuery.to_json())

# convert the object into a dict
ip_intelligence_response_query_dict = ip_intelligence_response_query_instance.to_dict()
# create an instance of IpIntelligenceResponseQuery from a dict
ip_intelligence_response_query_from_dict = IpIntelligenceResponseQuery.from_dict(ip_intelligence_response_query_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


