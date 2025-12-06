# TrackingConfig

Change tracking configuration for an indicator

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**enabled** | **bool** | Whether tracking is currently enabled | [optional] 
**fields** | **List[str]** | Fields being tracked for changes | [optional] 
**frequency** | **str** | Check frequency: hourly, daily, or weekly | [optional] 
**created_at** | **datetime** | When tracking was first started | [optional] 
**last_check** | **datetime** | When the last check was performed | [optional] 
**next_check** | **datetime** | When the next check is scheduled | [optional] 
**username** | **str** | Username of the owner | [optional] 
**type** | **str** | Indicator type: ip or domain | [optional] 
**value** | **str** | Indicator value | [optional] 

## Example

```python
from whisper_api_sdk.models.tracking_config import TrackingConfig

# TODO update the JSON string below
json = "{}"
# create an instance of TrackingConfig from a JSON string
tracking_config_instance = TrackingConfig.from_json(json)
# print the JSON string representation of the object
print(TrackingConfig.to_json())

# convert the object into a dict
tracking_config_dict = tracking_config_instance.to_dict()
# create an instance of TrackingConfig from a dict
tracking_config_from_dict = TrackingConfig.from_dict(tracking_config_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


