# MonitorCheckResponse

Monitoring check details

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Unique identifier for the check | [optional] 
**name** | **str** | Name of the monitoring check | [optional] 
**url** | **str** | URL being monitored | [optional] 
**type** | **str** | Type of check | [optional] 
**status** | **str** | Current status | [optional] 
**enabled** | **bool** | Whether the check is enabled | [optional] 
**frequency** | **int** | Check frequency in minutes | [optional] 
**locations** | **List[str]** | Locations where check runs | [optional] 
**muted** | **bool** | Whether the check is muted (no alerts) | [optional] 
**method** | **str** | HTTP method used for API checks | [optional] 
**assertions** | [**MonitorAssertions**](MonitorAssertions.md) | Assertions configured for this check | [optional] 
**last_run_at** | **datetime** | Last time the check ran | [optional] 
**created_at** | **datetime** | When the check was created | [optional] 
**updated_at** | **datetime** | When the check was last updated | [optional] 
**uptime24_hours** | **float** | Uptime percentage over the last 24 hours | [optional] 
**uptime7_days** | **float** | Uptime percentage over the last 7 days | [optional] 
**uptime30_days** | **float** | Uptime percentage over the last 30 days | [optional] 
**response_time** | **int** | Average response time in milliseconds | [optional] 

## Example

```python
from whisper_api_sdk.models.monitor_check_response import MonitorCheckResponse

# TODO update the JSON string below
json = "{}"
# create an instance of MonitorCheckResponse from a JSON string
monitor_check_response_instance = MonitorCheckResponse.from_json(json)
# print the JSON string representation of the object
print(MonitorCheckResponse.to_json())

# convert the object into a dict
monitor_check_response_dict = monitor_check_response_instance.to_dict()
# create an instance of MonitorCheckResponse from a dict
monitor_check_response_from_dict = MonitorCheckResponse.from_dict(monitor_check_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


