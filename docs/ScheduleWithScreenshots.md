# ScheduleWithScreenshots

A schedule with its captured screenshots

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**schedule_id** | **str** | Schedule ID | [optional] 
**url** | **str** | URL being captured | [optional] 
**screenshots** | [**List[ScreenshotEntry]**](ScreenshotEntry.md) | List of captured screenshots | [optional] 

## Example

```python
from whisper_api_sdk.models.schedule_with_screenshots import ScheduleWithScreenshots

# TODO update the JSON string below
json = "{}"
# create an instance of ScheduleWithScreenshots from a JSON string
schedule_with_screenshots_instance = ScheduleWithScreenshots.from_json(json)
# print the JSON string representation of the object
print(ScheduleWithScreenshots.to_json())

# convert the object into a dict
schedule_with_screenshots_dict = schedule_with_screenshots_instance.to_dict()
# create an instance of ScheduleWithScreenshots from a dict
schedule_with_screenshots_from_dict = ScheduleWithScreenshots.from_dict(schedule_with_screenshots_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


