# MonitoringStatusResponse

Monitoring status and metrics for a target domain or IP

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**target** | **str** | The target domain or IP being monitored | [optional] 
**status** | **str** | Current monitoring status | [optional] 
**metrics** | [**MonitoringMetrics**](MonitoringMetrics.md) | Monitoring metrics and statistics | [optional] 

## Example

```python
from whisper_api_sdk.models.monitoring_status_response import MonitoringStatusResponse

# TODO update the JSON string below
json = "{}"
# create an instance of MonitoringStatusResponse from a JSON string
monitoring_status_response_instance = MonitoringStatusResponse.from_json(json)
# print the JSON string representation of the object
print(MonitoringStatusResponse.to_json())

# convert the object into a dict
monitoring_status_response_dict = monitoring_status_response_instance.to_dict()
# create an instance of MonitoringStatusResponse from a dict
monitoring_status_response_from_dict = MonitoringStatusResponse.from_dict(monitoring_status_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


