# BenchmarkInfo

Benchmark metadata

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data_as_of** | **str** | Data freshness timestamp | [optional] 
**sample_size** | **int** | Sample size for benchmark | [optional] 
**collection_period** | **str** | Data collection period | [optional] 

## Example

```python
from whisper_api_sdk.models.benchmark_info import BenchmarkInfo

# TODO update the JSON string below
json = "{}"
# create an instance of BenchmarkInfo from a JSON string
benchmark_info_instance = BenchmarkInfo.from_json(json)
# print the JSON string representation of the object
print(BenchmarkInfo.to_json())

# convert the object into a dict
benchmark_info_dict = benchmark_info_instance.to_dict()
# create an instance of BenchmarkInfo from a dict
benchmark_info_from_dict = BenchmarkInfo.from_dict(benchmark_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


