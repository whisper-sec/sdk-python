# DomainerStringListResponse

Response containing a list of strings

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**results** | **List[str]** | List of string results | [optional] 

## Example

```python
from noctis_frontgraph_sdk.models.domainer_string_list_response import DomainerStringListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of DomainerStringListResponse from a JSON string
domainer_string_list_response_instance = DomainerStringListResponse.from_json(json)
# print the JSON string representation of the object
print(DomainerStringListResponse.to_json())

# convert the object into a dict
domainer_string_list_response_dict = domainer_string_list_response_instance.to_dict()
# create an instance of DomainerStringListResponse from a dict
domainer_string_list_response_from_dict = DomainerStringListResponse.from_dict(domainer_string_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


