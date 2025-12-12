# BenchmarkMetrics

Key security metrics

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**average_risk_score** | **float** | Average risk score | [optional] 
**mttd_hours** | **float** | Mean time to detect (hours) | [optional] 
**mttr_hours** | **float** | Mean time to respond (hours) | [optional] 
**detection_rate** | **float** | Detection rate percentage | [optional] 
**false_positive_rate** | **float** | False positive rate percentage | [optional] 
**incidents_per_month** | **float** | Average incidents per month | [optional] 

## Example

```python
from whisper_api_sdk.models.benchmark_metrics import BenchmarkMetrics

# TODO update the JSON string below
json = "{}"
# create an instance of BenchmarkMetrics from a JSON string
benchmark_metrics_instance = BenchmarkMetrics.from_json(json)
# print the JSON string representation of the object
print(BenchmarkMetrics.to_json())

# convert the object into a dict
benchmark_metrics_dict = benchmark_metrics_instance.to_dict()
# create an instance of BenchmarkMetrics from a dict
benchmark_metrics_from_dict = BenchmarkMetrics.from_dict(benchmark_metrics_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


