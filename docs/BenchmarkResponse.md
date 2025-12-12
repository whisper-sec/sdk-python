# BenchmarkResponse

Industry-wide security benchmark metrics for peer comparison

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | [**QueryInfo**](QueryInfo.md) | Query metadata | [optional] 
**industry** | [**IndustryInfo**](IndustryInfo.md) | Industry identification | [optional] 
**metrics** | [**BenchmarkMetrics**](BenchmarkMetrics.md) | Benchmark metrics | [optional] 
**percentiles** | [**PercentileInfo**](PercentileInfo.md) | Percentile rankings | [optional] 
**threat_profile** | [**ThreatProfile**](ThreatProfile.md) | Industry threat profile | [optional] 
**trends** | [**TrendData**](TrendData.md) | Trend data over time | [optional] 
**benchmark_info** | [**BenchmarkInfo**](BenchmarkInfo.md) | Benchmark metadata | [optional] 

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


