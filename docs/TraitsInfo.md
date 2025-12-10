# TraitsInfo

IP classification and behavioral traits

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**user_type** | **str** | Classification of the IP address based on its typical use | [optional] 
**is_anonymous_proxy** | **bool** | Whether this IP is associated with anonymous proxy services | [optional] 
**is_tor_exit_node** | **bool** | Whether this IP is a known Tor exit node | [optional] 
**is_vpn** | **bool** | Whether this IP is associated with a VPN service | [optional] 

## Example

```python
from whisper_api_sdk.models.traits_info import TraitsInfo

# TODO update the JSON string below
json = "{}"
# create an instance of TraitsInfo from a JSON string
traits_info_instance = TraitsInfo.from_json(json)
# print the JSON string representation of the object
print(TraitsInfo.to_json())

# convert the object into a dict
traits_info_dict = traits_info_instance.to_dict()
# create an instance of TraitsInfo from a dict
traits_info_from_dict = TraitsInfo.from_dict(traits_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


