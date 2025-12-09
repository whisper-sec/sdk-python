# ScreenshotSchedule

A scheduled screenshot configuration

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Unique identifier for this schedule | [optional] 
**url** | **str** | The URL to capture screenshots of | [optional] 
**username** | **str** | Username/API key owner of this schedule | [optional] 
**cron** | **str** | Cron expression for scheduling (mutually exclusive with frequency) | [optional] 
**frequency** | **str** | Frequency preset (mutually exclusive with cron). Use one of the preset values for simplified scheduling. | [optional] 
**timezone** | **str** | Timezone for the schedule | [optional] 
**enabled** | **bool** | Whether this schedule is currently active | [optional] 
**options** | [**ScreenshotOptions**](ScreenshotOptions.md) | Screenshot options (width, height, format, etc.) | [optional] 
**created_at** | **datetime** | When this schedule was created | [optional] 
**updated_at** | **datetime** | When this schedule was last updated | [optional] 
**last_capture_at** | **datetime** | When the last screenshot was captured | [optional] 
**next_capture_at** | **datetime** | When the next screenshot is scheduled | [optional] 
**capture_count** | **int** | Total number of screenshots captured by this schedule | [optional] 

## Example

```python
from whisper_api_sdk.models.screenshot_schedule import ScreenshotSchedule

# TODO update the JSON string below
json = "{}"
# create an instance of ScreenshotSchedule from a JSON string
screenshot_schedule_instance = ScreenshotSchedule.from_json(json)
# print the JSON string representation of the object
print(ScreenshotSchedule.to_json())

# convert the object into a dict
screenshot_schedule_dict = screenshot_schedule_instance.to_dict()
# create an instance of ScreenshotSchedule from a dict
screenshot_schedule_from_dict = ScreenshotSchedule.from_dict(screenshot_schedule_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


