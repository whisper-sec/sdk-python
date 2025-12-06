# EarlyWarning

Early warning signal

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **str** | Warning type | [optional] 
**severity** | **str** | Severity level | [optional] 
**message** | **str** | Warning message | [optional] 
**detected_at** | **str** | Detection timestamp | [optional] 

## Example

```python
from whisper_api_sdk.models.early_warning import EarlyWarning

# TODO update the JSON string below
json = "{}"
# create an instance of EarlyWarning from a JSON string
early_warning_instance = EarlyWarning.from_json(json)
# print the JSON string representation of the object
print(EarlyWarning.to_json())

# convert the object into a dict
early_warning_dict = early_warning_instance.to_dict()
# create an instance of EarlyWarning from a dict
early_warning_from_dict = EarlyWarning.from_dict(early_warning_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


