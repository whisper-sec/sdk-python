# MonitorResultListResponse

Response containing a list of check execution results

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**check_id** | **str** | ID of the check these results belong to | [optional] 
**count** | **int** | Total number of results returned | [optional] 
**results** | [**List[MonitorResultResponse]**](MonitorResultResponse.md) | List of check execution results | [optional] 

## Example

```python
from whisper_api_sdk.models.monitor_result_list_response import MonitorResultListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of MonitorResultListResponse from a JSON string
monitor_result_list_response_instance = MonitorResultListResponse.from_json(json)
# print the JSON string representation of the object
print(MonitorResultListResponse.to_json())

# convert the object into a dict
monitor_result_list_response_dict = monitor_result_list_response_instance.to_dict()
# create an instance of MonitorResultListResponse from a dict
monitor_result_list_response_from_dict = MonitorResultListResponse.from_dict(monitor_result_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


