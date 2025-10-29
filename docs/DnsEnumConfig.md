# DnsEnumConfig

Configuration for DNS enumeration and subdomain discovery

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**subdomain_enum** | **bool** | Enable subdomain enumeration | [optional] [default to True]
**zone_transfer** | **bool** | Enable DNS zone transfer attempts | [optional] [default to False]
**reverse_dns** | **bool** | Enable reverse DNS lookups | [optional] [default to True]
**wordlist_size** | **str** | Wordlist size for subdomain brute-forcing | [optional] [default to 'medium']

## Example

```python
from whisper_api_sdk.models.dns_enum_config import DnsEnumConfig

# TODO update the JSON string below
json = "{}"
# create an instance of DnsEnumConfig from a JSON string
dns_enum_config_instance = DnsEnumConfig.from_json(json)
# print the JSON string representation of the object
print(DnsEnumConfig.to_json())

# convert the object into a dict
dns_enum_config_dict = dns_enum_config_instance.to_dict()
# create an instance of DnsEnumConfig from a dict
dns_enum_config_from_dict = DnsEnumConfig.from_dict(dns_enum_config_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


