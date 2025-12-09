# DomainItem

A single domain entry in the search results

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**domain** | **str** | The domain name | 

## Example

```python
from whisper_api_sdk.models.domain_item import DomainItem

# TODO update the JSON string below
json = "{}"
# create an instance of DomainItem from a JSON string
domain_item_instance = DomainItem.from_json(json)
# print the JSON string representation of the object
print(DomainItem.to_json())

# convert the object into a dict
domain_item_dict = domain_item_instance.to_dict()
# create an instance of DomainItem from a dict
domain_item_from_dict = DomainItem.from_dict(domain_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


