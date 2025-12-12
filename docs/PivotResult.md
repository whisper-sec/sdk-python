# PivotResult

Result of AI infrastructure pivoting

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicator** | **str** | The starting indicator for pivoting | [optional] 
**indicator_type** | **str** | Type of the starting indicator | [optional] 
**depth** | **int** | Depth of pivot operation | [optional] 
**status** | **str** | Status of the pivot operation | [optional] 
**error** | **bool** | Whether an error occurred | [optional] 
**message** | **str** | Error message if the pivot failed | [optional] 
**pivot** | **object** |  | [optional] 

## Example

```python
from whisper_api_sdk.models.pivot_result import PivotResult

# TODO update the JSON string below
json = "{}"
# create an instance of PivotResult from a JSON string
pivot_result_instance = PivotResult.from_json(json)
# print the JSON string representation of the object
print(PivotResult.to_json())

# convert the object into a dict
pivot_result_dict = pivot_result_instance.to_dict()
# create an instance of PivotResult from a dict
pivot_result_from_dict = PivotResult.from_dict(pivot_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


