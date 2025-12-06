# PercentileInfo

Percentile distribution

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**p25** | **float** | 25th percentile risk score | [optional] 
**p50** | **float** | 50th percentile risk score (median) | [optional] 
**p75** | **float** | 75th percentile risk score | [optional] 
**p90** | **float** | 90th percentile risk score | [optional] 

## Example

```python
from whisper_api_sdk.models.percentile_info import PercentileInfo

# TODO update the JSON string below
json = "{}"
# create an instance of PercentileInfo from a JSON string
percentile_info_instance = PercentileInfo.from_json(json)
# print the JSON string representation of the object
print(PercentileInfo.to_json())

# convert the object into a dict
percentile_info_dict = percentile_info_instance.to_dict()
# create an instance of PercentileInfo from a dict
percentile_info_from_dict = PercentileInfo.from_dict(percentile_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


