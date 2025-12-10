# GraphNode

A node in the infrastructure graph representing a domain, IP, ASN, or other entity

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Unique identifier for the node (typically the domain name, IP address, or ASN) | [optional] 
**type** | **str** | Type of infrastructure element this node represents | [optional] 
**label** | **str** | Human-readable label for display (may differ from id) | [optional] 
**properties** | **Dict[str, object]** | Additional properties for node styling or filtering | [optional] 

## Example

```python
from whisper_api_sdk.models.graph_node import GraphNode

# TODO update the JSON string below
json = "{}"
# create an instance of GraphNode from a JSON string
graph_node_instance = GraphNode.from_json(json)
# print the JSON string representation of the object
print(GraphNode.to_json())

# convert the object into a dict
graph_node_dict = graph_node_instance.to_dict()
# create an instance of GraphNode from a dict
graph_node_from_dict = GraphNode.from_dict(graph_node_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


