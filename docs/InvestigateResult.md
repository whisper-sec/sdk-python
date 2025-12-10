# InvestigateResult

Result of an AI-powered threat investigation

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicator** | **str** | The indicator that was investigated | [optional] 
**indicator_type** | **str** | Type of the indicator | [optional] 
**status** | **str** | Status of the investigation | [optional] 
**error** | **bool** | Whether an error occurred during investigation | [optional] 
**message** | **str** | Error message if the investigation failed | [optional] 
**investigation** | **object** |  | [optional] 

## Example

```python
from whisper_api_sdk.models.investigate_result import InvestigateResult

# TODO update the JSON string below
json = "{}"
# create an instance of InvestigateResult from a JSON string
investigate_result_instance = InvestigateResult.from_json(json)
# print the JSON string representation of the object
print(InvestigateResult.to_json())

# convert the object into a dict
investigate_result_dict = investigate_result_instance.to_dict()
# create an instance of InvestigateResult from a dict
investigate_result_from_dict = InvestigateResult.from_dict(investigate_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


