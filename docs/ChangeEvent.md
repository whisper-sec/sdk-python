# ChangeEvent

A single detected change event

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**timestamp** | **datetime** | When the change was detected | [optional] 
**var_field** | **str** | Field that changed (dot notation, e.g., &#39;dns.a_record&#39;) | [optional] 
**old_value** | **object** |  | [optional] 
**new_value** | **object** |  | [optional] 
**category** | **str** | Category of the change (dns, whois, ssl, etc.) | [optional] 
**severity** | **str** | Severity of the change: low, medium, high | [optional] 

## Example

```python
from whisper_api_sdk.models.change_event import ChangeEvent

# TODO update the JSON string below
json = "{}"
# create an instance of ChangeEvent from a JSON string
change_event_instance = ChangeEvent.from_json(json)
# print the JSON string representation of the object
print(ChangeEvent.to_json())

# convert the object into a dict
change_event_dict = change_event_instance.to_dict()
# create an instance of ChangeEvent from a dict
change_event_from_dict = ChangeEvent.from_dict(change_event_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


