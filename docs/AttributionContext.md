# AttributionContext

Attribution context information

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**observed_ttps** | **List[str]** | Observed MITRE ATT&amp;CK TTPs | [optional] 
**targeted_sector** | **str** | Targeted sector/industry | [optional] 
**target_region** | **str** | Geographic region of targets | [optional] 
**timeframe** | **str** | Campaign timeframe | [optional] 
**malware_families** | **List[str]** | Known malware families observed | [optional] 

## Example

```python
from whisper_api_sdk.models.attribution_context import AttributionContext

# TODO update the JSON string below
json = "{}"
# create an instance of AttributionContext from a JSON string
attribution_context_instance = AttributionContext.from_json(json)
# print the JSON string representation of the object
print(AttributionContext.to_json())

# convert the object into a dict
attribution_context_dict = attribution_context_instance.to_dict()
# create an instance of AttributionContext from a dict
attribution_context_from_dict = AttributionContext.from_dict(attribution_context_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


