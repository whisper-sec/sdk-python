# SimilarDomainEntry

A single similar domain entry with its detection technique

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain** | **str** | The similar domain name. For homoglyph/IDN domains, may include punycode in parentheses. | 
**technique** | **str** | The similarity detection technique that found this domain | 

## Example

```python
from whisper_api_sdk.models.similar_domain_entry import SimilarDomainEntry

# TODO update the JSON string below
json = "{}"
# create an instance of SimilarDomainEntry from a JSON string
similar_domain_entry_instance = SimilarDomainEntry.from_json(json)
# print the JSON string representation of the object
print(SimilarDomainEntry.to_json())

# convert the object into a dict
similar_domain_entry_dict = similar_domain_entry_instance.to_dict()
# create an instance of SimilarDomainEntry from a dict
similar_domain_entry_from_dict = SimilarDomainEntry.from_dict(similar_domain_entry_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


