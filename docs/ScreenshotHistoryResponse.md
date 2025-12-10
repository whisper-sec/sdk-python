# ScreenshotHistoryResponse

Response containing screenshot history for a target URL

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**target** | **str** | The target domain or URL queried | [optional] 
**schedules** | [**List[ScheduleWithScreenshots]**](ScheduleWithScreenshots.md) | List of schedules that captured screenshots of this target | [optional] 
**total_screenshots** | **int** | Total number of screenshots available for this target | [optional] 
**limit** | **int** | Maximum number of screenshots returned (limit parameter) | [optional] 

## Example

```python
from whisper_api_sdk.models.screenshot_history_response import ScreenshotHistoryResponse

# TODO update the JSON string below
json = "{}"
# create an instance of ScreenshotHistoryResponse from a JSON string
screenshot_history_response_instance = ScreenshotHistoryResponse.from_json(json)
# print the JSON string representation of the object
print(ScreenshotHistoryResponse.to_json())

# convert the object into a dict
screenshot_history_response_dict = screenshot_history_response_instance.to_dict()
# create an instance of ScreenshotHistoryResponse from a dict
screenshot_history_response_from_dict = ScreenshotHistoryResponse.from_dict(screenshot_history_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


