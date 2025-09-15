# IpIntelligenceResponseGeolocationCountry


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**iso_code** | **str** | ISO 3166-1 alpha-2 code | [optional] 
**name** | **str** | Country name | [optional] 
**confidence** | **int** | Confidence score (0-100) | [optional] 

## Example

```python
from noctis_frontgraph_sdk.models.ip_intelligence_response_geolocation_country import IpIntelligenceResponseGeolocationCountry

# TODO update the JSON string below
json = "{}"
# create an instance of IpIntelligenceResponseGeolocationCountry from a JSON string
ip_intelligence_response_geolocation_country_instance = IpIntelligenceResponseGeolocationCountry.from_json(json)
# print the JSON string representation of the object
print(IpIntelligenceResponseGeolocationCountry.to_json())

# convert the object into a dict
ip_intelligence_response_geolocation_country_dict = ip_intelligence_response_geolocation_country_instance.to_dict()
# create an instance of IpIntelligenceResponseGeolocationCountry from a dict
ip_intelligence_response_geolocation_country_from_dict = IpIntelligenceResponseGeolocationCountry.from_dict(ip_intelligence_response_geolocation_country_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


