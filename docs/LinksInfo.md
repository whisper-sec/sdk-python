# LinksInfo

Link statistics and top sources/destinations

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total** | **int** | Total number of links | [optional] 
**top_sources** | **List[str]** | Top linking sources (for incoming links) | [optional] 
**top_destinations** | **List[str]** | Top link destinations (for outgoing links) | [optional] 

## Example

```python
from whisper_api_sdk.models.links_info import LinksInfo

# TODO update the JSON string below
json = "{}"
# create an instance of LinksInfo from a JSON string
links_info_instance = LinksInfo.from_json(json)
# print the JSON string representation of the object
print(LinksInfo.to_json())

# convert the object into a dict
links_info_dict = links_info_instance.to_dict()
# create an instance of LinksInfo from a dict
links_info_from_dict = LinksInfo.from_dict(links_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


