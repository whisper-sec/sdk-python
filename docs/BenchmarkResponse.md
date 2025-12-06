# BenchmarkResponse

Industry-wide security benchmark metrics for peer comparison

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | [**QueryInfo**](QueryInfo.md) |  | [optional] 
**industry** | [**IndustryInfo**](IndustryInfo.md) |  | [optional] 
**metrics** | [**BenchmarkMetrics**](BenchmarkMetrics.md) |  | [optional] 
**percentiles** | [**PercentileInfo**](PercentileInfo.md) |  | [optional] 
**threat_profile** | [**ThreatProfile**](ThreatProfile.md) |  | [optional] 
**trends** | [**TrendData**](TrendData.md) |  | [optional] 
**benchmark_info** | [**BenchmarkInfo**](BenchmarkInfo.md) |  | [optional] 

## Example

```python
from whisper_api_sdk.models.benchmark_response import BenchmarkResponse

# TODO update the JSON string below
json = "{}"
# create an instance of BenchmarkResponse from a JSON string
benchmark_response_instance = BenchmarkResponse.from_json(json)
# print the JSON string representation of the object
print(BenchmarkResponse.to_json())

# convert the object into a dict
benchmark_response_dict = benchmark_response_instance.to_dict()
# create an instance of BenchmarkResponse from a dict
benchmark_response_from_dict = BenchmarkResponse.from_dict(benchmark_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


