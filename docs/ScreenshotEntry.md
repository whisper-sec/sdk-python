# ScreenshotEntry

An individual screenshot capture record

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**url** | **str** | URL to download the screenshot image | [optional] 
**captured_at** | **datetime** | When the screenshot was captured | [optional] 
**format** | **str** | Image format | [optional] 
**dimensions** | **str** | Image dimensions in pixels | [optional] 
**file_size** | **int** | File size in bytes | [optional] 

## Example

```python
from whisper_api_sdk.models.screenshot_entry import ScreenshotEntry

# TODO update the JSON string below
json = "{}"
# create an instance of ScreenshotEntry from a JSON string
screenshot_entry_instance = ScreenshotEntry.from_json(json)
# print the JSON string representation of the object
print(ScreenshotEntry.to_json())

# convert the object into a dict
screenshot_entry_dict = screenshot_entry_instance.to_dict()
# create an instance of ScreenshotEntry from a dict
screenshot_entry_from_dict = ScreenshotEntry.from_dict(screenshot_entry_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


