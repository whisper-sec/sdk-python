# PredictiveRiskResponse

ML-based predictive risk assessment for an indicator

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | [**QueryInfo**](QueryInfo.md) | Query metadata | [optional] 
**current_assessment** | [**CurrentAssessment**](CurrentAssessment.md) | Current risk assessment | [optional] 
**predictions** | [**Predictions**](Predictions.md) | Future risk predictions | [optional] 
**trajectory** | [**TrajectoryInfo**](TrajectoryInfo.md) | Risk trajectory details | [optional] 
**risk_factors** | [**List[RiskFactor]**](RiskFactor.md) | Contributing risk factors | [optional] 
**pattern_matching** | [**PatternMatching**](PatternMatching.md) | Pattern matching insights | [optional] 
**early_warnings** | [**List[EarlyWarning]**](EarlyWarning.md) | Early warning signals | [optional] 
**similar_cases** | [**List[SimilarCase]**](SimilarCase.md) | Similar historical cases | [optional] 
**model_info** | [**ModelInfo**](ModelInfo.md) | ML model information | [optional] 

## Example

```python
from whisper_api_sdk.models.predictive_risk_response import PredictiveRiskResponse

# TODO update the JSON string below
json = "{}"
# create an instance of PredictiveRiskResponse from a JSON string
predictive_risk_response_instance = PredictiveRiskResponse.from_json(json)
# print the JSON string representation of the object
print(PredictiveRiskResponse.to_json())

# convert the object into a dict
predictive_risk_response_dict = predictive_risk_response_instance.to_dict()
# create an instance of PredictiveRiskResponse from a dict
predictive_risk_response_from_dict = PredictiveRiskResponse.from_dict(predictive_risk_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


