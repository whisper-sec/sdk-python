# CountryInfo

Country-level geographic information

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**iso_code** | **str** | ISO 3166-1 alpha-2 country code | [optional] 
**name** | **str** | Full country name in English | [optional] 
**confidence** | **int** | Confidence score for country detection (0-100) | [optional] 

## Example

```python
from whisper_api_sdk.models.country_info import CountryInfo

# TODO update the JSON string below
json = "{}"
# create an instance of CountryInfo from a JSON string
country_info_instance = CountryInfo.from_json(json)
# print the JSON string representation of the object
print(CountryInfo.to_json())

# convert the object into a dict
country_info_dict = country_info_instance.to_dict()
# create an instance of CountryInfo from a dict
country_info_from_dict = CountryInfo.from_dict(country_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


