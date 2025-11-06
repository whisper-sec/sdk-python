# ScreenshotOptions

Configuration options for screenshot capture

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**width** | **int** | Viewport width in pixels | [optional] [default to 1920]
**height** | **int** | Viewport height in pixels | [optional] [default to 1080]
**full_page** | **bool** | Capture the full page height (scrolling screenshot) | [optional] [default to False]
**wait_time** | **int** | Wait time in milliseconds before taking screenshot | [optional] [default to 2000]
**format** | **str** | Image format for the screenshot | [optional] [default to 'png']
**quality** | **int** | Image quality (1-100, only for jpeg/webp) | [optional] [default to 90]
**user_agent** | **str** | User agent string to use for the request | [optional] 
**javascript** | **bool** | Enable JavaScript execution | [optional] [default to True]
**block_ads** | **bool** | Block ads and trackers | [optional] [default to False]
**accept_cookies** | **bool** | Accept cookies consent if prompted | [optional] [default to True]

## Example

```python
from whisper_api_sdk.models.screenshot_options import ScreenshotOptions

# TODO update the JSON string below
json = "{}"
# create an instance of ScreenshotOptions from a JSON string
screenshot_options_instance = ScreenshotOptions.from_json(json)
# print the JSON string representation of the object
print(ScreenshotOptions.to_json())

# convert the object into a dict
screenshot_options_dict = screenshot_options_instance.to_dict()
# create an instance of ScreenshotOptions from a dict
screenshot_options_from_dict = ScreenshotOptions.from_dict(screenshot_options_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


