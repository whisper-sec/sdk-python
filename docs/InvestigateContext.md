# InvestigateContext

Additional investigation context

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**hypothesis** | **str** | Initial hypothesis or suspicion | [optional] 
**related_indicators** | **List[str]** | Related indicators to consider | [optional] 
**time_range** | **str** | Time range for analysis | [optional] 

## Example

```python
from whisper_api_sdk.models.investigate_context import InvestigateContext

# TODO update the JSON string below
json = "{}"
# create an instance of InvestigateContext from a JSON string
investigate_context_instance = InvestigateContext.from_json(json)
# print the JSON string representation of the object
print(InvestigateContext.to_json())

# convert the object into a dict
investigate_context_dict = investigate_context_instance.to_dict()
# create an instance of InvestigateContext from a dict
investigate_context_from_dict = InvestigateContext.from_dict(investigate_context_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


