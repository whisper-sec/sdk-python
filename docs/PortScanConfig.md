# PortScanConfig

Configuration for port scanning

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ports** | **str** | Ports to scan (comma-separated or range) | [optional] [default to 'top-1000']
**technique** | **str** | Scan technique | [optional] [default to 'syn']
**threads** | **int** | Number of parallel threads | [optional] [default to 10]
**port_timeout** | **int** | Timeout per port in milliseconds | [optional] [default to 1000]

## Example

```python
from whisper_api_sdk.models.port_scan_config import PortScanConfig

# TODO update the JSON string below
json = "{}"
# create an instance of PortScanConfig from a JSON string
port_scan_config_instance = PortScanConfig.from_json(json)
# print the JSON string representation of the object
print(PortScanConfig.to_json())

# convert the object into a dict
port_scan_config_dict = port_scan_config_instance.to_dict()
# create an instance of PortScanConfig from a dict
port_scan_config_from_dict = PortScanConfig.from_dict(port_scan_config_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


