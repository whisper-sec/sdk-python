# ServiceDiscoveryConfig

Configuration for service and version detection

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**version_detection** | **bool** | Enable service version detection | [optional] [default to True]
**os_detection** | **bool** | Enable OS fingerprinting | [optional] [default to False]
**intensity** | **int** | Aggressiveness of service detection (1-9) | [optional] [default to 5]
**script_scan** | **bool** | Enable script scanning | [optional] [default to False]

## Example

```python
from whisper_api_sdk.models.service_discovery_config import ServiceDiscoveryConfig

# TODO update the JSON string below
json = "{}"
# create an instance of ServiceDiscoveryConfig from a JSON string
service_discovery_config_instance = ServiceDiscoveryConfig.from_json(json)
# print the JSON string representation of the object
print(ServiceDiscoveryConfig.to_json())

# convert the object into a dict
service_discovery_config_dict = service_discovery_config_instance.to_dict()
# create an instance of ServiceDiscoveryConfig from a dict
service_discovery_config_from_dict = ServiceDiscoveryConfig.from_dict(service_discovery_config_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


