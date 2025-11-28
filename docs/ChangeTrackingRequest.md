# ChangeTrackingRequest

Request to start or update change tracking for an indicator

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**fields** | **List[str]** | Fields to track for changes. Valid values depend on indicator type. | [optional] 
**frequency** | **str** | How often to check for changes | [optional] 
**enabled** | **bool** | Whether tracking is enabled | [optional] 

## Example

```python
from whisper_api_sdk.models.change_tracking_request import ChangeTrackingRequest

# TODO update the JSON string below
json = "{}"
# create an instance of ChangeTrackingRequest from a JSON string
change_tracking_request_instance = ChangeTrackingRequest.from_json(json)
# print the JSON string representation of the object
print(ChangeTrackingRequest.to_json())

# convert the object into a dict
change_tracking_request_dict = change_tracking_request_instance.to_dict()
# create an instance of ChangeTrackingRequest from a dict
change_tracking_request_from_dict = ChangeTrackingRequest.from_dict(change_tracking_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


