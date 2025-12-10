# GraphLink

A link/edge connecting two nodes in the infrastructure graph

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source** | **str** | ID of the source node (where the relationship originates) | [optional] 
**target** | **str** | ID of the target node (where the relationship points to) | [optional] 
**type** | **str** | Type of relationship between the nodes | [optional] 
**weight** | **float** | Weight or strength of the relationship (for layout algorithms) | [optional] 
**properties** | **Dict[str, object]** | Additional properties for link styling or filtering | [optional] 

## Example

```python
from whisper_api_sdk.models.graph_link import GraphLink

# TODO update the JSON string below
json = "{}"
# create an instance of GraphLink from a JSON string
graph_link_instance = GraphLink.from_json(json)
# print the JSON string representation of the object
print(GraphLink.to_json())

# convert the object into a dict
graph_link_dict = graph_link_instance.to_dict()
# create an instance of GraphLink from a dict
graph_link_from_dict = GraphLink.from_dict(graph_link_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


