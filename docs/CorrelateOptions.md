# CorrelateOptions

Configuration options for correlation analysis. This is an OBJECT, not a string. All fields are optional. 

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**time_window** | **str** | Time window for temporal correlation. Format: number + unit (d&#x3D;days, w&#x3D;weeks, m&#x3D;months). Examples: 7d, 2w, 3m | [optional] 
**correlation_types** | **List[str]** | Types of correlation to analyze. Possible values: infrastructure, campaign, actor, malware, technique | [optional] 
**min_confidence** | **float** | Minimum confidence threshold for correlations (0.0 to 1.0). Higher values return fewer but more confident results. | [optional] 
**include_industry_breakdown** | **bool** | Include breakdown of indicator prevalence by industry sector in the response. | [optional] 

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


