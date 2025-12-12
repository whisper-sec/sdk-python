# ScreenshotScheduleConfig

Configuration for scheduling recurring screenshot captures.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**cron** | **str** | Cron expression for scheduling (advanced). Use frequency for simpler configuration. | [optional] 
**frequency** | **str** | Frequency of captures. Use one of the preset values or provide a cron expression for custom schedules. | [optional] 
**timezone** | **str** | Timezone for scheduled captures | [optional] [default to 'UTC']
**retention_count** | **int** | Maximum number of captures to retain | [optional] [default to 30]
**enabled** | **bool** | Enable/disable the schedule | [optional] [default to True]

## Example

```python
from whisper_api_sdk.models.screenshot_schedule_config import ScreenshotScheduleConfig

# TODO update the JSON string below
json = "{}"
# create an instance of ScreenshotScheduleConfig from a JSON string
screenshot_schedule_config_instance = ScreenshotScheduleConfig.from_json(json)
# print the JSON string representation of the object
print(ScreenshotScheduleConfig.to_json())

# convert the object into a dict
screenshot_schedule_config_dict = screenshot_schedule_config_instance.to_dict()
# create an instance of ScreenshotScheduleConfig from a dict
screenshot_schedule_config_from_dict = ScreenshotScheduleConfig.from_dict(screenshot_schedule_config_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


