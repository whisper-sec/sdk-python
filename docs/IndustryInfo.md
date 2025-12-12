# IndustryInfo

Industry identification

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**code** | **str** | Industry code | [optional] 
**description** | **str** | Industry description | [optional] 
**display_name** | **str** | Display name | [optional] 

## Example

```python
from whisper_api_sdk.models.industry_info import IndustryInfo

# TODO update the JSON string below
json = "{}"
# create an instance of IndustryInfo from a JSON string
industry_info_instance = IndustryInfo.from_json(json)
# print the JSON string representation of the object
print(IndustryInfo.to_json())

# convert the object into a dict
industry_info_dict = industry_info_instance.to_dict()
# create an instance of IndustryInfo from a dict
industry_info_from_dict = IndustryInfo.from_dict(industry_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


