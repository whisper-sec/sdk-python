# ScanOptions

Advanced configuration options for infrastructure scanning

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**port_scan** | [**PortScanConfig**](PortScanConfig.md) |  | [optional] 
**service_discovery** | [**ServiceDiscoveryConfig**](ServiceDiscoveryConfig.md) |  | [optional] 
**vulnerability** | [**VulnerabilityConfig**](VulnerabilityConfig.md) |  | [optional] 
**dns_enum** | [**DnsEnumConfig**](DnsEnumConfig.md) |  | [optional] 

## Example

```python
from whisper_api_sdk.models.scan_options import ScanOptions

# TODO update the JSON string below
json = "{}"
# create an instance of ScanOptions from a JSON string
scan_options_instance = ScanOptions.from_json(json)
# print the JSON string representation of the object
print(ScanOptions.to_json())

# convert the object into a dict
scan_options_dict = scan_options_instance.to_dict()
# create an instance of ScanOptions from a dict
scan_options_from_dict = ScanOptions.from_dict(scan_options_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


