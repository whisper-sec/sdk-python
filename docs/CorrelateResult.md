# CorrelateResult

Result of global indicator correlation analysis

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicators** | **List[str]** | List of indicators that were correlated | [optional] 
**status** | **str** | Status of the correlation analysis | [optional] 
**error** | **bool** | Whether an error occurred | [optional] 
**message** | **str** | Error message if the correlation failed | [optional] 
**correlation** | **object** |  | [optional] 

## Example

```python
from whisper_api_sdk.models.correlate_result import CorrelateResult

# TODO update the JSON string below
json = "{}"
# create an instance of CorrelateResult from a JSON string
correlate_result_instance = CorrelateResult.from_json(json)
# print the JSON string representation of the object
print(CorrelateResult.to_json())

# convert the object into a dict
correlate_result_dict = correlate_result_instance.to_dict()
# create an instance of CorrelateResult from a dict
correlate_result_from_dict = CorrelateResult.from_dict(correlate_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


