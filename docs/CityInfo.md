# CityInfo

City-level geographic information

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | Normalized city name (lowercase) | [optional] 
**original_name** | **str** | Original city name with proper capitalization | [optional] 
**confidence** | **int** | Confidence score for city detection (0-100) | [optional] 

## Example

```python
from whisper_api_sdk.models.city_info import CityInfo

# TODO update the JSON string below
json = "{}"
# create an instance of CityInfo from a JSON string
city_info_instance = CityInfo.from_json(json)
# print the JSON string representation of the object
print(CityInfo.to_json())

# convert the object into a dict
city_info_dict = city_info_instance.to_dict()
# create an instance of CityInfo from a dict
city_info_from_dict = CityInfo.from_dict(city_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


