# ScreenshotScheduleListResponse

Response containing a list of screenshot schedules and quota information

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** | Number of schedules in this response | [optional] 
**max_schedules** | **int** | Maximum number of schedules allowed per API key | [optional] 
**max_screenshots_per_schedule** | **int** | Maximum number of screenshots retained per schedule | [optional] 
**schedules** | [**List[ScreenshotSchedule]**](ScreenshotSchedule.md) | List of screenshot schedules | [optional] 

## Example

```python
from whisper_api_sdk.models.screenshot_schedule_list_response import ScreenshotScheduleListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of ScreenshotScheduleListResponse from a JSON string
screenshot_schedule_list_response_instance = ScreenshotScheduleListResponse.from_json(json)
# print the JSON string representation of the object
print(ScreenshotScheduleListResponse.to_json())

# convert the object into a dict
screenshot_schedule_list_response_dict = screenshot_schedule_list_response_instance.to_dict()
# create an instance of ScreenshotScheduleListResponse from a dict
screenshot_schedule_list_response_from_dict = ScreenshotScheduleListResponse.from_dict(screenshot_schedule_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


