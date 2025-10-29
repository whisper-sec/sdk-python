# JobError


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**code** | **str** |  | [optional] 
**message** | **str** |  | [optional] 
**details** | **str** |  | [optional] 
**timestamp** | **datetime** |  | [optional] 

## Example

```python
from whisper_api_sdk.models.job_error import JobError

# TODO update the JSON string below
json = "{}"
# create an instance of JobError from a JSON string
job_error_instance = JobError.from_json(json)
# print the JSON string representation of the object
print(JobError.to_json())

# convert the object into a dict
job_error_dict = job_error_instance.to_dict()
# create an instance of JobError from a dict
job_error_from_dict = JobError.from_dict(job_error_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


