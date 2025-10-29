# DomainReputationScores

Domain reputation calculated from infrastructure IP scores

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**overall_score** | **float** | Overall reputation score (0-100, higher &#x3D; more suspicious) | [optional] 
**risk_level** | **str** | Risk classification based on overall score | [optional] 
**domain_ip_score** | **float** | Average IP reputation score for domain&#39;s A records | [optional] 
**nameserver_ip_score** | **float** | Average IP reputation score for nameserver IPs | [optional] 
**mailserver_ip_score** | **float** | Average IP reputation score for mail server IPs | [optional] 
**details** | [**DomainReputationDetails**](DomainReputationDetails.md) |  | [optional] 
**scoring_method** | **str** | Scoring methodology used | [optional] 
**weights** | **Dict[str, float]** | Weighting strategy applied to infrastructure components | [optional] 

## Example

```python
from whisper_api_sdk.models.domain_reputation_scores import DomainReputationScores

# TODO update the JSON string below
json = "{}"
# create an instance of DomainReputationScores from a JSON string
domain_reputation_scores_instance = DomainReputationScores.from_json(json)
# print the JSON string representation of the object
print(DomainReputationScores.to_json())

# convert the object into a dict
domain_reputation_scores_dict = domain_reputation_scores_instance.to_dict()
# create an instance of DomainReputationScores from a dict
domain_reputation_scores_from_dict = DomainReputationScores.from_dict(domain_reputation_scores_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


