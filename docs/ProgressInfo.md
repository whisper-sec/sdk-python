# ProgressInfo

Job progress information

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**current** | **int** | Current progress value | [optional] 
**total** | **int** | Total expected progress value | [optional] 
**message** | **str** | Progress message | [optional] 

## Example

```python
from whisper_api_sdk.models.progress_info import ProgressInfo

# TODO update the JSON string below
json = "{}"
# create an instance of ProgressInfo from a JSON string
progress_info_instance = ProgressInfo.from_json(json)
# print the JSON string representation of the object
print(ProgressInfo.to_json())

# convert the object into a dict
progress_info_dict = progress_info_instance.to_dict()
# create an instance of ProgressInfo from a dict
progress_info_from_dict = ProgressInfo.from_dict(progress_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


