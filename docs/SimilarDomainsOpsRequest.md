# SimilarDomainsOpsRequest

Request for generating similar/lookalike domains for brand protection

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain** | **str** | The target domain to generate variations for | 
**techniques** | **str** | Techniques to use for generating similar domains. Supported values: typosquatting, homoglyph, bitsquatting, tld_variation, sounding, prefix, suffix, contains, levenshtein. If not specified, defaults to typosquatting. | [optional] 
**limit** | **int** | Maximum number of similar domains to return per technique | [optional] 
**options** | **object** |  | [optional] 

## Example

```python
from whisper_api_sdk.models.similar_domains_ops_request import SimilarDomainsOpsRequest

# TODO update the JSON string below
json = "{}"
# create an instance of SimilarDomainsOpsRequest from a JSON string
similar_domains_ops_request_instance = SimilarDomainsOpsRequest.from_json(json)
# print the JSON string representation of the object
print(SimilarDomainsOpsRequest.to_json())

# convert the object into a dict
similar_domains_ops_request_dict = similar_domains_ops_request_instance.to_dict()
# create an instance of SimilarDomainsOpsRequest from a dict
similar_domains_ops_request_from_dict = SimilarDomainsOpsRequest.from_dict(similar_domains_ops_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


