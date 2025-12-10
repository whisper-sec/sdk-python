# MonitorResultResponse

Result of a single check execution

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**timestamp** | **datetime** | When the check was executed | [optional] 
**success** | **bool** | Whether the check passed | [optional] 
**location** | **str** | Location where check ran | [optional] 
**attempt** | **int** | Check attempt number (for retries) | [optional] 
**check_id** | **str** | ID of the check this result belongs to | [optional] 
**result_id** | **str** | Unique result ID | [optional] 
**response_time** | **int** | Response time in milliseconds | [optional] 
**status_code** | **int** | HTTP status code received | [optional] 
**error_message** | **str** | Error message if check failed | [optional] 
**has_errors** | **bool** | Whether check ran from all locations | [optional] 

## Example

```python
from whisper_api_sdk.models.monitor_result_response import MonitorResultResponse

# TODO update the JSON string below
json = "{}"
# create an instance of MonitorResultResponse from a JSON string
monitor_result_response_instance = MonitorResultResponse.from_json(json)
# print the JSON string representation of the object
print(MonitorResultResponse.to_json())

# convert the object into a dict
monitor_result_response_dict = monitor_result_response_instance.to_dict()
# create an instance of MonitorResultResponse from a dict
monitor_result_response_from_dict = MonitorResultResponse.from_dict(monitor_result_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


