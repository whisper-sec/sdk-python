# PredictionPoint

A single prediction point

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**confidence** | **float** | Prediction confidence (0-1) | [optional] 
**predicted_score** | **float** | Predicted risk score | [optional] 
**predicted_level** | **str** | Predicted risk level | [optional] 

## Example

```python
from whisper_api_sdk.models.prediction_point import PredictionPoint

# TODO update the JSON string below
json = "{}"
# create an instance of PredictionPoint from a JSON string
prediction_point_instance = PredictionPoint.from_json(json)
# print the JSON string representation of the object
print(PredictionPoint.to_json())

# convert the object into a dict
prediction_point_dict = prediction_point_instance.to_dict()
# create an instance of PredictionPoint from a dict
prediction_point_from_dict = PredictionPoint.from_dict(prediction_point_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


