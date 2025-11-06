# InfrastructureMapRequest

Configuration for mapping infrastructure relationships and discovering connected assets

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**start_point** | **str** | Starting point for infrastructure mapping (domain or IP address) | 
**depth** | **int** | Depth of relationship mapping (number of hops from starting point). Depth 1: Direct relationships (~30s, 10-50 assets), Depth 2: 2 hops (~2-5 min, 50-500 assets), Depth 3: 3 hops (~10-30 min, 500-5000 assets) | [optional] [default to 1]

## Example

```python
from whisper_api_sdk.models.infrastructure_map_request import InfrastructureMapRequest

# TODO update the JSON string below
json = "{}"
# create an instance of InfrastructureMapRequest from a JSON string
infrastructure_map_request_instance = InfrastructureMapRequest.from_json(json)
# print the JSON string representation of the object
print(InfrastructureMapRequest.to_json())

# convert the object into a dict
infrastructure_map_request_dict = infrastructure_map_request_instance.to_dict()
# create an instance of InfrastructureMapRequest from a dict
infrastructure_map_request_from_dict = InfrastructureMapRequest.from_dict(infrastructure_map_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


