# SimilarDomainRequest

Configuration for generating similar domain variations for brand protection and threat hunting

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**techniques** | **List[str]** | Types of domain variations to generate | [optional] 
**limit** | **int** | Maximum number of similar domains to generate | [optional] [default to 100]
**check_registration** | **bool** | Check if generated domains are registered | [optional] [default to False]
**include_dns** | **bool** | Include DNS resolution data for registered domains | [optional] [default to False]
**include_risk_score** | **bool** | Calculate risk scores for each variation | [optional] [default to True]
**technique_config** | [**TechniqueConfig**](TechniqueConfig.md) |  | [optional] 

## Example

```python
from whisper_api_sdk.models.similar_domain_request import SimilarDomainRequest

# TODO update the JSON string below
json = "{}"
# create an instance of SimilarDomainRequest from a JSON string
similar_domain_request_instance = SimilarDomainRequest.from_json(json)
# print the JSON string representation of the object
print(SimilarDomainRequest.to_json())

# convert the object into a dict
similar_domain_request_dict = similar_domain_request_instance.to_dict()
# create an instance of SimilarDomainRequest from a dict
similar_domain_request_from_dict = SimilarDomainRequest.from_dict(similar_domain_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


