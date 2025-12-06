# CorrelateOptions

Correlation analysis options

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**time_window** | **str** | Time window for temporal correlation | [optional] 
**correlation_types** | **List[str]** | Types of correlation to analyze | [optional] 
**min_confidence** | **float** | Minimum confidence threshold | [optional] 
**include_industry_breakdown** | **bool** | Include industry breakdown | [optional] 

## Example

```python
from whisper_api_sdk.models.correlate_options import CorrelateOptions

# TODO update the JSON string below
json = "{}"
# create an instance of CorrelateOptions from a JSON string
correlate_options_instance = CorrelateOptions.from_json(json)
# print the JSON string representation of the object
print(CorrelateOptions.to_json())

# convert the object into a dict
correlate_options_dict = correlate_options_instance.to_dict()
# create an instance of CorrelateOptions from a dict
correlate_options_from_dict = CorrelateOptions.from_dict(correlate_options_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


