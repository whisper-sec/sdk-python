# IpIntelligenceResponseGeolocation

Geolocation data with confidence scores

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**country** | [**IpIntelligenceResponseGeolocationCountry**](IpIntelligenceResponseGeolocationCountry.md) |  | [optional] 
**coordinates** | [**IpIntelligenceResponseGeolocationCoordinates**](IpIntelligenceResponseGeolocationCoordinates.md) |  | [optional] 

## Example

```python
from noctis_frontgraph_sdk.models.ip_intelligence_response_geolocation import IpIntelligenceResponseGeolocation

# TODO update the JSON string below
json = "{}"
# create an instance of IpIntelligenceResponseGeolocation from a JSON string
ip_intelligence_response_geolocation_instance = IpIntelligenceResponseGeolocation.from_json(json)
# print the JSON string representation of the object
print(IpIntelligenceResponseGeolocation.to_json())

# convert the object into a dict
ip_intelligence_response_geolocation_dict = ip_intelligence_response_geolocation_instance.to_dict()
# create an instance of IpIntelligenceResponseGeolocation from a dict
ip_intelligence_response_geolocation_from_dict = IpIntelligenceResponseGeolocation.from_dict(ip_intelligence_response_geolocation_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


