# MonitorCheckRequest

Request to create or update a monitoring check

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | Name of the monitoring check | 
**url** | **str** | URL to monitor | 
**type** | **str** | Type of check: api, ssl, or dns | [optional] 
**frequency** | **int** | Check frequency in minutes | [optional] 
**locations** | **List[str]** | Locations to run checks from | [optional] 
**assertions** | [**MonitorAssertions**](MonitorAssertions.md) | Assertions for the check | [optional] 
**enabled** | **bool** | Whether the check is enabled | [optional] 
**method** | **str** | HTTP method for API checks | [optional] 
**headers** | **Dict[str, str]** | Request headers for API checks | [optional] 
**body** | **str** | Request body for POST/PUT API checks | [optional] 

## Example

```python
from whisper_api_sdk.models.monitor_check_request import MonitorCheckRequest

# TODO update the JSON string below
json = "{}"
# create an instance of MonitorCheckRequest from a JSON string
monitor_check_request_instance = MonitorCheckRequest.from_json(json)
# print the JSON string representation of the object
print(MonitorCheckRequest.to_json())

# convert the object into a dict
monitor_check_request_dict = monitor_check_request_instance.to_dict()
# create an instance of MonitorCheckRequest from a dict
monitor_check_request_from_dict = MonitorCheckRequest.from_dict(monitor_check_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


