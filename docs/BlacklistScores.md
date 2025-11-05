# BlacklistScores

Blacklist scores at different network levels

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ip_score** | **float** | IP-level blacklist score | [optional] 
**prefix_score** | **float** | Network prefix blacklist score | [optional] 
**asn_score** | **float** | ASN-level blacklist score | [optional] 

## Example

```python
from whisper_api_sdk.models.blacklist_scores import BlacklistScores

# TODO update the JSON string below
json = "{}"
# create an instance of BlacklistScores from a JSON string
blacklist_scores_instance = BlacklistScores.from_json(json)
# print the JSON string representation of the object
print(BlacklistScores.to_json())

# convert the object into a dict
blacklist_scores_dict = blacklist_scores_instance.to_dict()
# create an instance of BlacklistScores from a dict
blacklist_scores_from_dict = BlacklistScores.from_dict(blacklist_scores_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


