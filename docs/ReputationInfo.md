# ReputationInfo

Reputation scoring and blacklist information for threat assessment

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**risk_score** | **float** | Composite risk score (0-10, higher &#x3D; riskier) | [optional] 
**blacklists** | [**BlacklistScores**](BlacklistScores.md) | Blacklist presence scores across various threat feeds | [optional] 
**domain_reputation** | [**DomainReputationScores**](DomainReputationScores.md) | Domain reputation based on infrastructure IP scoring (domains only) | [optional] 

## Example

```python
from whisper_api_sdk.models.reputation_info import ReputationInfo

# TODO update the JSON string below
json = "{}"
# create an instance of ReputationInfo from a JSON string
reputation_info_instance = ReputationInfo.from_json(json)
# print the JSON string representation of the object
print(ReputationInfo.to_json())

# convert the object into a dict
reputation_info_dict = reputation_info_instance.to_dict()
# create an instance of ReputationInfo from a dict
reputation_info_from_dict = ReputationInfo.from_dict(reputation_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


