# ScreenshotRequest

Request parameters for capturing a website screenshot

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**url** | **str** | The URL of the website to capture | 
**options** | [**ScreenshotOptions**](ScreenshotOptions.md) |  | [optional] 
**schedule** | [**ScheduleConfig**](ScheduleConfig.md) |  | [optional] 

## Example

```python
from whisper_api_sdk.models.screenshot_request import ScreenshotRequest

# TODO update the JSON string below
json = "{}"
# create an instance of ScreenshotRequest from a JSON string
screenshot_request_instance = ScreenshotRequest.from_json(json)
# print the JSON string representation of the object
print(ScreenshotRequest.to_json())

# convert the object into a dict
screenshot_request_dict = screenshot_request_instance.to_dict()
# create an instance of ScreenshotRequest from a dict
screenshot_request_from_dict = ScreenshotRequest.from_dict(screenshot_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


