# CurrentAssessment

Current risk state

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**confidence** | **float** | Confidence in assessment (0-1) | [optional] 
**risk_score** | **float** | Current risk score (0-100) | [optional] 
**risk_level** | **str** | Risk level category | [optional] 
**assessed_at** | **str** | Assessment timestamp | [optional] 

## Example

```python
from whisper_api_sdk.models.current_assessment import CurrentAssessment

# TODO update the JSON string below
json = "{}"
# create an instance of CurrentAssessment from a JSON string
current_assessment_instance = CurrentAssessment.from_json(json)
# print the JSON string representation of the object
print(CurrentAssessment.to_json())

# convert the object into a dict
current_assessment_dict = current_assessment_instance.to_dict()
# create an instance of CurrentAssessment from a dict
current_assessment_from_dict = CurrentAssessment.from_dict(current_assessment_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


