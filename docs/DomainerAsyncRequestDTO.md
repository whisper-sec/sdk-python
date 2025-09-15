# DomainerAsyncRequestDTO

Parameters for an asynchronous domain search (either similarity or free-text)

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain_name** | **str** | (Required for SIMILARITY requests) Domain name to search for similar domains | [optional] 
**similarity_type** | **str** | (Required for SIMILARITY requests) Type of similarity to use: CONTAINS, SOUNDING, PREFIX, SUFFIX, TYPO, UTFVARS | [optional] 
**query_string** | **str** | (Required for SEARCH requests) Query string (supports standard query syntax) | [optional] 
**operator** | **str** | (Optional for SEARCH requests) Default operator between query terms if not specified | [optional] [default to 'AND']
**level** | **str** | (Optional for SEARCH requests) Filter results by absolute domain level (dot count) | [optional] [default to 'ALL']
**find_available** | **bool** | Set to true to find AVAILABLE similar domains (typo/sounding) instead of existing ones. Requires domainName, ignores similarityType/queryString/operator/level. | [optional] [default to False]
**limit** | **int** | Maximum number of results to return (use a reasonable limit to prevent excessive processing) | [optional] [default to 100]
**callback_url** | **str** | URL to call with results when the search is complete (must be accessible from the server) | 

## Example

```python
from noctis_frontgraph_sdk.models.domainer_async_request_dto import DomainerAsyncRequestDTO

# TODO update the JSON string below
json = "{}"
# create an instance of DomainerAsyncRequestDTO from a JSON string
domainer_async_request_dto_instance = DomainerAsyncRequestDTO.from_json(json)
# print the JSON string representation of the object
print(DomainerAsyncRequestDTO.to_json())

# convert the object into a dict
domainer_async_request_dto_dict = domainer_async_request_dto_instance.to_dict()
# create an instance of DomainerAsyncRequestDTO from a dict
domainer_async_request_dto_from_dict = DomainerAsyncRequestDTO.from_dict(domainer_async_request_dto_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


