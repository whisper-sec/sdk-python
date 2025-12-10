# InvestigateContext

Additional context to guide and enhance the investigation. This is an OBJECT, not a string. All fields are optional. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**related_indicators** | **List[str]** | Related indicators (IPs, domains, hashes) to include in the investigation scope. Helps identify connections between indicators. | [optional] 
**hypothesis** | **str** | Initial hypothesis or suspicion to focus the investigation. The AI will attempt to prove or disprove this theory. | [optional] 
**time_range** | **str** | Time range for historical analysis. Format: number + unit (d&#x3D;days, w&#x3D;weeks, m&#x3D;months). Examples: 7d, 2w, 3m, 90d | [optional] 

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


