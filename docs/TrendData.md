# TrendData

Historical trend data

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**direction** | **str** | Trend direction | [optional] 
**risk_trend30d** | **str** | 30-day risk trend | [optional] 
**change_percent** | **float** | Risk score change percentage | [optional] 

## Example

```python
from whisper_api_sdk.models.trend_data import TrendData

# TODO update the JSON string below
json = "{}"
# create an instance of TrendData from a JSON string
trend_data_instance = TrendData.from_json(json)
# print the JSON string representation of the object
print(TrendData.to_json())

# convert the object into a dict
trend_data_dict = trend_data_instance.to_dict()
# create an instance of TrendData from a dict
trend_data_from_dict = TrendData.from_dict(trend_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


