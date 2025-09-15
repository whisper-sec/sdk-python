# DomainerAsyncResultDTO

Results and status information for an asynchronous domain search request (similarity or free-text)

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**request_id** | **str** | Unique identifier for the request | [readonly] 
**domain_name** | **str** | Domain name that was searched | [optional] [readonly] 
**similarity_type** | [**DomainerSimilarityType**](DomainerSimilarityType.md) |  | [optional] 
**query_string** | **str** | Query string used for the search (only for SEARCH requests) | [optional] [readonly] 
**operator** | **str** | Default operator used between query terms (only for SEARCH requests) | [optional] [readonly] 
**level** | **str** | Absolute domain level filter applied (only for SEARCH requests) | [optional] [readonly] 
**limit** | **int** | Maximum number of results requested | [readonly] 
**created_at** | **datetime** | Time when the request was created | [readonly] 
**completed_at** | **datetime** | Time when the request was completed (null if still processing) | [optional] [readonly] 
**status** | **str** | Request status | [readonly] 
**results** | **List[str]** | List of similar domains found (null if still processing) | [optional] [readonly] 
**result_count** | **int** | Total number of results found | [optional] [readonly] 
**processing_time_ms** | **int** | Time taken to process the request in milliseconds (-1 if still processing) | [optional] [readonly] 

## Example

```python
from noctis_frontgraph_sdk.models.domainer_async_result_dto import DomainerAsyncResultDTO

# TODO update the JSON string below
json = "{}"
# create an instance of DomainerAsyncResultDTO from a JSON string
domainer_async_result_dto_instance = DomainerAsyncResultDTO.from_json(json)
# print the JSON string representation of the object
print(DomainerAsyncResultDTO.to_json())

# convert the object into a dict
domainer_async_result_dto_dict = domainer_async_result_dto_instance.to_dict()
# create an instance of DomainerAsyncResultDTO from a dict
domainer_async_result_dto_from_dict = DomainerAsyncResultDTO.from_dict(domainer_async_result_dto_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


