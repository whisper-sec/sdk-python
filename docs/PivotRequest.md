# PivotRequest

Request for intelligent infrastructure pivoting and relationship discovery

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**indicator** | **str** | Starting indicator (IP address, domain, or hash) for pivot analysis | 
**indicator_type** | **str** | Type of the starting indicator. Must be one of: ip, domain, hash | 
**depth** | **int** | Pivot depth - how many hops to traverse from the starting indicator. Higher depth &#x3D; more results but longer processing time. | [optional] [default to 1]
**strategies** | **List[str]** | Pivot strategies to use. Possible values: dns (DNS relationships), whois (WHOIS data), ssl (SSL certificates), infrastructure (hosting), passive_dns (historical DNS) | [optional] 
**max_nodes** | **int** | Maximum number of related nodes/indicators to discover. Limits result size for performance. | [optional] [default to 100]

## Example

```python
from whisper_api_sdk.models.pivot_request import PivotRequest

# TODO update the JSON string below
json = "{}"
# create an instance of PivotRequest from a JSON string
pivot_request_instance = PivotRequest.from_json(json)
# print the JSON string representation of the object
print(PivotRequest.to_json())

# convert the object into a dict
pivot_request_dict = pivot_request_instance.to_dict()
# create an instance of PivotRequest from a dict
pivot_request_from_dict = PivotRequest.from_dict(pivot_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


