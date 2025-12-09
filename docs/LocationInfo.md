# LocationInfo

Detailed location information including coordinates and timezone

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**latitude** | **float** | Latitude coordinate | [optional] 
**longitude** | **float** | Longitude coordinate | [optional] 
**accuracy_radius** | **int** | Accuracy radius in kilometers - actual location is within this radius | [optional] 
**time_zone** | **str** | IANA timezone identifier | [optional] 

## Example

```python
from whisper_api_sdk.models.location_info import LocationInfo

# TODO update the JSON string below
json = "{}"
# create an instance of LocationInfo from a JSON string
location_info_instance = LocationInfo.from_json(json)
# print the JSON string representation of the object
print(LocationInfo.to_json())

# convert the object into a dict
location_info_dict = location_info_instance.to_dict()
# create an instance of LocationInfo from a dict
location_info_from_dict = LocationInfo.from_dict(location_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


