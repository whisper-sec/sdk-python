# DomainerAsyncResponseDTO

Response object for an asynchronous domain similarity search request submission

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**request_id** | **str** | Unique identifier for tracking the request | [readonly] 
**domain_name** | **str** | Domain name being searched | [readonly] 
**query_string** | **str** | Query string submitted for free-text search (if applicable) | [optional] [readonly] 
**message** | **str** | Status message providing information about the request | [readonly] 
**status_url** | **str** | URL to check for results (can be polled to monitor progress and get results) | [readonly] 

## Example

```python
from noctis_frontgraph_sdk.models.domainer_async_response_dto import DomainerAsyncResponseDTO

# TODO update the JSON string below
json = "{}"
# create an instance of DomainerAsyncResponseDTO from a JSON string
domainer_async_response_dto_instance = DomainerAsyncResponseDTO.from_json(json)
# print the JSON string representation of the object
print(DomainerAsyncResponseDTO.to_json())

# convert the object into a dict
domainer_async_response_dto_dict = domainer_async_response_dto_instance.to_dict()
# create an instance of DomainerAsyncResponseDTO from a dict
domainer_async_response_dto_from_dict = DomainerAsyncResponseDTO.from_dict(domainer_async_response_dto_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


