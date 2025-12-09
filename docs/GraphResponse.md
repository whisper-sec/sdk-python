# GraphResponse

Graph visualization data showing relationships between infrastructure elements. Format is compatible with react-force-graph, vis.js, cytoscape.js, and similar libraries.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**nodes** | [**List[GraphNode]**](GraphNode.md) | List of nodes (vertices) in the graph. Each node represents an infrastructure element. | [optional] 
**links** | [**List[GraphLink]**](GraphLink.md) | List of links (edges) connecting nodes. Each link represents a relationship between elements. | [optional] 
**total_nodes** | **int** | Total count of nodes before any limit was applied | [optional] 
**total_links** | **int** | Total count of links before any limit was applied | [optional] 

## Example

```python
from whisper_api_sdk.models.graph_response import GraphResponse

# TODO update the JSON string below
json = "{}"
# create an instance of GraphResponse from a JSON string
graph_response_instance = GraphResponse.from_json(json)
# print the JSON string representation of the object
print(GraphResponse.to_json())

# convert the object into a dict
graph_response_dict = graph_response_instance.to_dict()
# create an instance of GraphResponse from a dict
graph_response_from_dict = GraphResponse.from_dict(graph_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


