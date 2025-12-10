# IpGeolocationResponse

Geolocation and network information for an IP address

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ip** | **str** | The queried IP address | [optional] 
**country** | [**CountryInfo**](CountryInfo.md) | Country information | [optional] 
**city** | [**CityInfo**](CityInfo.md) | City information | [optional] 
**location** | [**LocationInfo**](LocationInfo.md) | Geographic location details | [optional] 
**isp** | [**IspInfo**](IspInfo.md) | Internet Service Provider and network information | [optional] 
**traits** | [**TraitsInfo**](TraitsInfo.md) | IP classification and traits | [optional] 
**coordinates** | [**CoordinatesInfo**](CoordinatesInfo.md) | Geographic coordinates (convenience field) | [optional] 

## Example

```python
from whisper_api_sdk.models.ip_geolocation_response import IpGeolocationResponse

# TODO update the JSON string below
json = "{}"
# create an instance of IpGeolocationResponse from a JSON string
ip_geolocation_response_instance = IpGeolocationResponse.from_json(json)
# print the JSON string representation of the object
print(IpGeolocationResponse.to_json())

# convert the object into a dict
ip_geolocation_response_dict = ip_geolocation_response_instance.to_dict()
# create an instance of IpGeolocationResponse from a dict
ip_geolocation_response_from_dict = IpGeolocationResponse.from_dict(ip_geolocation_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


