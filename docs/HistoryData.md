# HistoryData


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**records** | **List[object]** |  | [optional] 
**total_records** | **int** |  | [optional] 
**oldest_date** | **str** |  | [optional] 
**newest_date** | **str** |  | [optional] 
**message** | **str** |  | [optional] 

## Example

```python
from whisper_api_sdk.models.history_data import HistoryData

# TODO update the JSON string below
json = "{}"
# create an instance of HistoryData from a JSON string
history_data_instance = HistoryData.from_json(json)
# print the JSON string representation of the object
print(HistoryData.to_json())

# convert the object into a dict
history_data_dict = history_data_instance.to_dict()
# create an instance of HistoryData from a dict
history_data_from_dict = HistoryData.from_dict(history_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


