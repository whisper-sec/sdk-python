# MonitorListResponse

List of monitoring checks with summary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**checks** | [**List[MonitorCheckResponse]**](MonitorCheckResponse.md) | List of monitoring checks | [optional] 
**total** | **int** | Total number of checks | [optional] 
**passing** | **int** | Number of passing checks | [optional] 
**failing** | **int** | Number of failing checks | [optional] 
**degraded** | **int** | Number of degraded checks | [optional] 
**pending** | **int** | Number of pending checks (not yet run) | [optional] 

## Example

```python
from whisper_api_sdk.models.monitor_list_response import MonitorListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of MonitorListResponse from a JSON string
monitor_list_response_instance = MonitorListResponse.from_json(json)
# print the JSON string representation of the object
print(MonitorListResponse.to_json())

# convert the object into a dict
monitor_list_response_dict = monitor_list_response_instance.to_dict()
# create an instance of MonitorListResponse from a dict
monitor_list_response_from_dict = MonitorListResponse.from_dict(monitor_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


