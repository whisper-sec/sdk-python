# RelationshipInfo

Connections and relationships to other infrastructure and domains

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**incoming_links** | [**LinksInfo**](LinksInfo.md) |  | [optional] 
**outgoing_links** | [**LinksInfo**](LinksInfo.md) |  | [optional] 
**related_domains** | **List[str]** | Related domains (same owner, same network, similar content) | [optional] 
**shared_infrastructure** | **List[str]** | Other assets sharing the same infrastructure (IP, ASN, nameservers) | [optional] 

## Example

```python
from whisper_api_sdk.models.relationship_info import RelationshipInfo

# TODO update the JSON string below
json = "{}"
# create an instance of RelationshipInfo from a JSON string
relationship_info_instance = RelationshipInfo.from_json(json)
# print the JSON string representation of the object
print(RelationshipInfo.to_json())

# convert the object into a dict
relationship_info_dict = relationship_info_instance.to_dict()
# create an instance of RelationshipInfo from a dict
relationship_info_from_dict = RelationshipInfo.from_dict(relationship_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


