# SearchResponse

Result returned when a WHOIS search job completes. Access this via GET /v1/ops/jobs/{jobId} after the job status becomes COMPLETED.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source** | **str** | The data source that was searched | 
**query_type** | **str** | The type of query that was performed | 
**items** | [**List[DomainItem]**](DomainItem.md) | List of matching domains | 
**total** | **int** | Total number of matching records across all pages | 
**page_number** | **int** | Current page number (0-indexed) | 
**page_size** | **int** | Number of results per page | 
**total_pages** | **int** | Total number of pages available | 
**error** | **bool** | Error flag, present only when the search failed | [optional] 
**message** | **str** | Error message, present only when the search failed | [optional] 

## Example

```python
from whisper_api_sdk.models.search_response import SearchResponse

# TODO update the JSON string below
json = "{}"
# create an instance of SearchResponse from a JSON string
search_response_instance = SearchResponse.from_json(json)
# print the JSON string representation of the object
print(SearchResponse.to_json())

# convert the object into a dict
search_response_dict = search_response_instance.to_dict()
# create an instance of SearchResponse from a dict
search_response_from_dict = SearchResponse.from_dict(search_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


