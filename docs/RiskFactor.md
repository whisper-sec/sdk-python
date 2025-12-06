# RiskFactor

Individual risk factor

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**factor** | **str** | Factor name | [optional] 
**weight** | **float** | Factor weight (0-1) | [optional] 
**contribution** | **float** | Contribution to score | [optional] 
**description** | **str** | Factor description | [optional] 

## Example

```python
from whisper_api_sdk.models.risk_factor import RiskFactor

# TODO update the JSON string below
json = "{}"
# create an instance of RiskFactor from a JSON string
risk_factor_instance = RiskFactor.from_json(json)
# print the JSON string representation of the object
print(RiskFactor.to_json())

# convert the object into a dict
risk_factor_dict = risk_factor_instance.to_dict()
# create an instance of RiskFactor from a dict
risk_factor_from_dict = RiskFactor.from_dict(risk_factor_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


