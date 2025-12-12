# TrajectoryInfo

Risk trajectory analysis

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**trend** | **str** | Trend direction | [optional] 
**velocity** | **str** | Velocity of change | [optional] 
**stability** | **str** | Trend stability | [optional] 

## Example

```python
from whisper_api_sdk.models.trajectory_info import TrajectoryInfo

# TODO update the JSON string below
json = "{}"
# create an instance of TrajectoryInfo from a JSON string
trajectory_info_instance = TrajectoryInfo.from_json(json)
# print the JSON string representation of the object
print(TrajectoryInfo.to_json())

# convert the object into a dict
trajectory_info_dict = trajectory_info_instance.to_dict()
# create an instance of TrajectoryInfo from a dict
trajectory_info_from_dict = TrajectoryInfo.from_dict(trajectory_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


