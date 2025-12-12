# AttributionContext

Context information to improve threat actor attribution accuracy. All fields are optional but providing more context improves attribution quality. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**observed_ttps** | **List[str]** | Observed MITRE ATT&amp;CK technique IDs. See https://attack.mitre.org for reference. | [optional] 
**targeted_sector** | **str** | Targeted industry sector. Common values: financial, healthcare, government, technology, energy, retail, manufacturing | [optional] 
**target_region** | **str** | Geographic region of targets. Use ISO country codes or region names. | [optional] 
**timeframe** | **str** | Campaign timeframe for attribution. Format: &#39;YYYY-MM-DD to YYYY-MM-DD&#39; or descriptive like &#39;Q1 2024&#39; | [optional] 
**malware_families** | **List[str]** | Known malware families observed in the campaign. Helps narrow down threat actor candidates. | [optional] 

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


