# IpIntelligenceResponseGeolocationCoordinates


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**latitude** | **float** | Latitude | [optional] 
**longitude** | **float** | Longitude | [optional] 
**accuracy_radius** | **int** | Accuracy radius in kilometers | [optional] 
**time_zone** | **str** | IANA time zone | [optional] 

## Example

```python
from noctis_frontgraph_sdk.models.ip_intelligence_response_geolocation_coordinates import IpIntelligenceResponseGeolocationCoordinates

# TODO update the JSON string below
json = "{}"
# create an instance of IpIntelligenceResponseGeolocationCoordinates from a JSON string
ip_intelligence_response_geolocation_coordinates_instance = IpIntelligenceResponseGeolocationCoordinates.from_json(json)
# print the JSON string representation of the object
print(IpIntelligenceResponseGeolocationCoordinates.to_json())

# convert the object into a dict
ip_intelligence_response_geolocation_coordinates_dict = ip_intelligence_response_geolocation_coordinates_instance.to_dict()
# create an instance of IpIntelligenceResponseGeolocationCoordinates from a dict
ip_intelligence_response_geolocation_coordinates_from_dict = IpIntelligenceResponseGeolocationCoordinates.from_dict(ip_intelligence_response_geolocation_coordinates_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


