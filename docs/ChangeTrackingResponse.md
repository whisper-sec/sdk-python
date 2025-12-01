# ChangeTrackingResponse

Change tracking response with configuration and detected changes

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicator** | **str** | The indicator value (IP or domain) | [optional] 
**type** | **str** | Indicator type: ip or domain | [optional] 
**tracking** | [**TrackingConfig**](TrackingConfig.md) |  | [optional] 
**changes** | [**List[ChangeEvent]**](ChangeEvent.md) | List of detected changes | [optional] 
**baseline** | **object** |  | [optional] 
**baseline_captured_at** | **datetime** | When the baseline was captured | [optional] 
**total_changes** | **int** | Total number of changes detected | [optional] 
**error** | **str** | Error message if operation failed | [optional] 
**success** | **bool** | Whether the operation was successful | [optional] 

## Example

```python
from whisper_api_sdk.models.change_tracking_response import ChangeTrackingResponse

# TODO update the JSON string below
json = "{}"
# create an instance of ChangeTrackingResponse from a JSON string
change_tracking_response_instance = ChangeTrackingResponse.from_json(json)
# print the JSON string representation of the object
print(ChangeTrackingResponse.to_json())

# convert the object into a dict
change_tracking_response_dict = change_tracking_response_instance.to_dict()
# create an instance of ChangeTrackingResponse from a dict
change_tracking_response_from_dict = ChangeTrackingResponse.from_dict(change_tracking_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


