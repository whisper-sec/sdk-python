# DomainIntelligenceResponseQuery


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain** | **str** | Queried domain | [optional] 
**timestamp** | **datetime** | Query timestamp | [optional] 
**response_time_ms** | **int** | Response time in milliseconds | [optional] 

## Example

```python
from noctis_frontgraph_sdk.models.domain_intelligence_response_query import DomainIntelligenceResponseQuery

# TODO update the JSON string below
json = "{}"
# create an instance of DomainIntelligenceResponseQuery from a JSON string
domain_intelligence_response_query_instance = DomainIntelligenceResponseQuery.from_json(json)
# print the JSON string representation of the object
print(DomainIntelligenceResponseQuery.to_json())

# convert the object into a dict
domain_intelligence_response_query_dict = domain_intelligence_response_query_instance.to_dict()
# create an instance of DomainIntelligenceResponseQuery from a dict
domain_intelligence_response_query_from_dict = DomainIntelligenceResponseQuery.from_dict(domain_intelligence_response_query_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


