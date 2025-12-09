# TrackedIndicator

A tracked indicator with its configuration and status

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **str** | Indicator type: ip or domain | [optional] 
**value** | **str** | Indicator value | [optional] 
**enabled** | **bool** | Whether tracking is currently enabled | [optional] 
**frequency** | **str** | Check frequency: hourly, daily, weekly | [optional] 
**fields** | **List[str]** | Fields being tracked | [optional] 
**created_at** | **datetime** | When tracking was started | [optional] 
**last_check_at** | **datetime** | When the last check was performed | [optional] 
**next_check_at** | **datetime** | When the next check is scheduled | [optional] 
**total_changes** | **int** | Total number of changes detected | [optional] 

## Example

```python
from whisper_api_sdk.models.tracked_indicator import TrackedIndicator

# TODO update the JSON string below
json = "{}"
# create an instance of TrackedIndicator from a JSON string
tracked_indicator_instance = TrackedIndicator.from_json(json)
# print the JSON string representation of the object
print(TrackedIndicator.to_json())

# convert the object into a dict
tracked_indicator_dict = tracked_indicator_instance.to_dict()
# create an instance of TrackedIndicator from a dict
tracked_indicator_from_dict = TrackedIndicator.from_dict(tracked_indicator_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


