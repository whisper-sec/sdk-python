# Job


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** |  | [optional] 
**status** | **str** |  | [optional] 
**type** | **str** |  | [optional] 
**params** | **object** |  | [optional] 
**result** | **object** |  | [optional] 
**error** | [**JobError**](JobError.md) |  | [optional] 
**progress** | [**JobProgress**](JobProgress.md) |  | [optional] 
**created_at** | **datetime** |  | [optional] 
**updated_at** | **datetime** |  | [optional] 
**completed_at** | **datetime** |  | [optional] 
**metadata** | **Dict[str, str]** |  | [optional] 
**username** | **str** |  | [optional] 

## Example

```python
from whisper_api_sdk.models.job import Job

# TODO update the JSON string below
json = "{}"
# create an instance of Job from a JSON string
job_instance = Job.from_json(json)
# print the JSON string representation of the object
print(Job.to_json())

# convert the object into a dict
job_dict = job_instance.to_dict()
# create an instance of Job from a dict
job_from_dict = Job.from_dict(job_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


