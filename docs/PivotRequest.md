# PivotRequest

Request for intelligent infrastructure pivoting and relationship discovery

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicator** | **str** | Starting indicator for pivot analysis | 
**indicator_type** | **str** | Type of starting indicator | 
**depth** | **int** | Pivot depth (1-3) | [optional] 
**strategies** | **List[str]** | Pivot strategies to use | [optional] 
**max_nodes** | **int** | Maximum nodes to discover | [optional] 

## Example

```python
from whisper_api_sdk.models.pivot_request import PivotRequest

# TODO update the JSON string below
json = "{}"
# create an instance of PivotRequest from a JSON string
pivot_request_instance = PivotRequest.from_json(json)
# print the JSON string representation of the object
print(PivotRequest.to_json())

# convert the object into a dict
pivot_request_dict = pivot_request_instance.to_dict()
# create an instance of PivotRequest from a dict
pivot_request_from_dict = PivotRequest.from_dict(pivot_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


