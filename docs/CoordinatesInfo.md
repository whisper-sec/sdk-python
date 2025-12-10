# CoordinatesInfo

Geographic coordinates as a convenience object

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**latitude** | **float** | Latitude coordinate | [optional] 
**longitude** | **float** | Longitude coordinate | [optional] 

## Example

```python
from whisper_api_sdk.models.coordinates_info import CoordinatesInfo

# TODO update the JSON string below
json = "{}"
# create an instance of CoordinatesInfo from a JSON string
coordinates_info_instance = CoordinatesInfo.from_json(json)
# print the JSON string representation of the object
print(CoordinatesInfo.to_json())

# convert the object into a dict
coordinates_info_dict = coordinates_info_instance.to_dict()
# create an instance of CoordinatesInfo from a dict
coordinates_info_from_dict = CoordinatesInfo.from_dict(coordinates_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


